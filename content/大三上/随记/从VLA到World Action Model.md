---
title: 具身智能：从VLA到World Action Model
date: 2026-08-28
tags:
  - VLA
  - 具身智能
  - WAM
---

# 具身智能：从 VLA 到 World Action Model

> 启程吧，现在阳光正好，现在的脚步正轻盈。


## 课程总览

本节以一个具体模型 **World Action Model（WAM）**——具体代表为 **Motors**——为主线，从宏观层面梳理具身智能（Embodied Intelligence）的整体技术路线。核心循环为：

```
观察（相机+本体状态）→ 理解（语义对齐）→ 想象（预测未来观测）→ 行动（输出 action chunk）→ 执行（控制器）→ 新观察 → 循环
```

将"把蓝色杯子放到篮子里"这一任务拆解，可分为三步：
1. **看懂**：通过 head camera 把语言指令与视觉空间对齐（语义+像素级对齐）
2. **想象**：预测执行当前动作后，未来世界会变成什么样（world model）
3. **行动**：输出一个 action chunk（tensor），送入控制器让机器人动起来

---

## 一、问题建模

定义：
- $o_t$：当前时刻的视觉观测
- $l$：语言指令
- $a_{t+1:t+K}$：未来 K 步动作
- $o_{t+1:t+K}$：未来 K 步视频观测

由此衍生出四类建模方式：

| 模型 | 输入 | 输出 | 特点 |
|---|---|---|---|
| **VLA**（Vision-Language-Action） | $o_t$, $l$ | $a_{t+1:t+K}$ | 推理最快，直接端到端输出动作 |
| **World Model** | $o_t$, $a_{t+1:t+K}$ | $o_{t+1:t+K}$ | 理解世界运行规律，想象未来 |
| **IDM**（Inverse Dynamic Model） | $o_t$, $o_{t+1:t+K}$ | $a_{t+1:t+K}$ | 已知想要的变化，反推需要什么动作 |
| **Video Generation Model** | $o_t$, $l$ | $o_{t+1:t+K}$ | 纯视频生成，如 Sora、Veo |
| **WAM**（World Action Model） | $o_t$, $l$ | $o_{t+1:t+K}$ **+** $a_{t+1:t+K}$ | 视频与动作联合建模，效果更好 |

WAM 的核心是**联合建模**：同时输出未来一段时间的观测（视频）和动作（action chunk），两者通过 Joint Attention 一同处理，没有先后依赖。

---

## 二、模型架构：Motors 的 Mixture-of-Transformers

Motors 采用 **Mixture of Transformers** 架构，由三个独立的 Transformer expert 组成：

### 三个 Expert

1. **Understanding Expert**：基于 Qwen3-VL 改造
   - 输入：language + 当前帧 observation
   - 负责视觉-语言对齐

2. **Video Generation Expert**：基于 Wan（千万级）视频生成模型
   - 输入：当前以噪声形式存在的未来帧
   - 经过 forward 后输出清晰的未来视频

3. **Action Expert**：与 Video Generation Expert 同深度的 Transformer action branch
   - 负责动作回归

### Joint Attention 机制

每个 Transformer 都有自己的 Norm 和 MLP，但在 Attention 层采用 **Joint Attention**：

- **传统 Self-Attention**：Q/K/V 来自同一模态（如 video），K^V^V^V
- **Joint Attention**：Q 来自某一模态，K/V 来自**所有模态**（video + action + understanding 的拼接）
- 效果：每个模态在每一层都保留自己的专属内容，同时在 Attention 中可访问其他所有模态的全部信息

> 这意味着 Motors 同时给出了具身智能的一个"目录/地图"：要解决哪些子问题，就去对应研究哪个 expert。

---

## 三、第一步：Understanding Expert —— 多模态基础

目标：语言说"蓝杯"，模型锁定图像中对应的像素块。

### 3.1 Vision Transformer 基础

把图像 patchify 成 token 序列 → 送入 Transformer 做 KQV + mask → 信息流通后理解整图。

### 3.2 VLM 的两种集成方式

- **前缀拼接**（代表：Qwen-VL）：直接把 vision token 拼到大语言模型的输入前缀中
- **Cross Attention**（代表：Flamingo）：通过 cross attention 融合视觉与语言

### 3.3 常用视觉编码器

| 编码器 | 特点 | 应用代表 |
|---|---|---|
| **DINO** | 能清晰感知物体结构与轮廓 | 强调物体边界 |
| **CLIP / SigLIP** | 图文对齐能力强 | OpenVLA 同时输入 DINO + SigLIP |
| **Qwen-VL** | 直接作为 VLM backbone | Motors Understanding Expert |

---

## 四、第二步：策略建模

### 4.1 最简单的 VLA：以 OpenVLA 为例

模型架构（可视为改造 VLM）：

```
image_observation + language_instruction
        │
   ┌────┴────┐
 DINO      SigLIP
   └────┬────┘
      projector
        │
      Llama (纯大语言模型)
        │
   decode → action token
        │
   解码为关节角 / 末端位姿
```

关键改造：把 Llama 输出的 language token 直接替换为 action token，训练后即得到 VLA。

**典型代表**：OpenVLA、RT-2、Physical Intelligence 的 **π0**（已迭代至 π0.7，仍采用 VLA 架构）。

### 4.2 行为克隆（Behavior Cloning）= 机器人版的 SFT

**训练目标**：

$$\max_\theta \prod_i p_\theta(a_i^* | o_i, l)$$

即给定专家示范数据，让模型最大化在当前参数下复现专家动作的概率，用 MSE 损失训练。

**两大固有问题**：

1. **均值压缩**：训练数据中一半从左绕、一半从右绕，MSE 训练会让动作落在"中间"——这往往是错的
2. **分布外崩溃**：专家数据全是正确分布，部署时若机器人手抖、状态偏移出训练分布，模型"没见过"，直接懵掉

> **核心 Tip**：训练策略不能只给正确数据，还要给大量"烂数据"（包括扰动、偏移），才能训出鲁棒模型。

### 4.3 Diffusion Policy

把动作生成建模为去噪过程：
- **训练**：真实动作加噪 → 模型预测噪声 → 损失衡量预测质量
- **推理**：从随机噪声出发 → 反复去噪 → 得到干净动作

天然支持**多模态动作分布**：同一指令可生成多种合理动作（类似生成多种狗的图片都对）。

### 4.4 Flow Matching（Motors 所用）

Motors 实际使用的是 **Rectified Flow**（而非标准 Diffusion）：

| 维度 | Diffusion (SDE) | Rectified Flow (ODE) |
|---|---|---|
| 过程类型 | 随机微分方程 | 常微分方程 |
| 训练稳定性 | 一般 | 更稳定 |
| 采样步数 | 多 | 可大幅减少 |
| 代表 | DDPM/DDIM | π0、Motors |

> 数学原理与 Diffusion 接近，建模层面差异显著：连续建模、训练稳定、可少步采样。

---

## 五、第三步：从预测未来到 World Action Model

### 5.1 三条技术路线演进

| 路线 | 思路 | 代表工作 | 问题 |
|---|---|---|---|
| **路线 1：纯策略**（VLA） | 观测+指令 → 动作，完全不预测未来 | OpenVLA、RT-2、π0 | 与视频生成无关 |
| **路线 2：视频规划**（Video Planning） | 先生成未来视频 → 再用 IDM 反解动作 | UniPi、VBP | 两阶段误差累积；推理慢；有前后依赖 |
| **路线 3：Latent Action** | 从视频帧间变化中无监督学到"潜动作" | LAPA、VIDA | 实现复杂，但可充分利用大规模视频数据 |
| **路线 4：WAM**（联合建模） | 视频与动作同步生成，Joint Attention 一体化 | Motors、NeroVLA、DreamZero | 集大成 |

### 5.2 为什么需要 Latent Action？

**核心矛盾**：具身智能最缺的恰恰是动作数据。

- 文本、图像、视频在互联网上极其丰富
- 但带"具体哪个关节角是多少"标签的动作数据**极少**
- 且不同机器人本体不同，action 数据**无法跨本体迁移**

**Latent Action 的解决思路**：
- 输入：相邻两帧图像
- 目标：从中无监督学习一个潜空间中的"动作表示"
- 常用方法：
  - **VA-VAE** 风格编码（LAPA）
  - **光流（Optical Flow）**：直接取像素级 delta 作为 latent action 表示
- 训练完成后，用少量带真实 action 标签的数据完成对齐

> 这使得模型可利用 YouTube 上大量"人手操作物体"的视频数据，大幅扩展训练语料。

---

## 六、第四步：Motors 的 Latent Action 实现

Motors 用 **Optical Flow 作为 pixel-level delta action**：

```
相邻帧 → 计算 optical flow → encoder 压缩为 latent action
                                            ↓
                              decoder 解码 + reconstruction loss（类似 VAE）
                                            ↓
                              用 latent action 训练 action expert
```

这与 Diffusion / VAE 课程中讲过的重建损失思想一致——核心目的都是**让模型从无动作标签的视频中学到有意义的动作表示**。

---

## 七、具身数据金字塔

Motors 构建的训练数据金字塔，越上层数据越稀缺但越贴合当前任务：

| 层级 | 数据类型 | 规模 | 重要性 |
|---|---|---|---|
| **L1 顶层** | Target robot + Target task 的 trajectory data | 极少 | 当前任务最关键 |
| L2 | 当前任务 + 其他机器人的数据 | 少 | 重要 |
| L3 | 跨任务合成数据（simulation） | 中 | 中等 |
| L4 | Ego data（人手操作视频） | 大 | 重要 |
| **L5 底层** | Web data（文本、视频） | 海量 | 基础 |

### Motors 的具体训练流程（L1 → L5）

1. **L1+L2（Prior）**：用 Web data 训练 VLM（Understanding Expert）和 Video Generation Model
2. **L3（Video Dynamics）**：用 **Something-Something v2（235）** 等与机器人操作高度相关的视频，对 Video Generation Model 做领域适配；摆脱"什么视频都看、生成动画片"的尴尬
3. **L4（Action Expert）**：冻结 Video + Language Model（它们已足够好，只需提供信息），用大量 Latent Action 训练 Action Expert
4. **L5（Fine-tune）**：在 Target robot + Target task 的具体轨迹数据上微调

### 跨本体（Cross-Embodiment）问题

不同机器人本体形态不同（人形 vs 双臂），希望同一份数据能复用。**Open X-Embodiment** 是代表性工作，主要思路：
- 统一多种数据格式
- 不存绝对关节参数，改存**相对量**（位移、增量）

> 这一问题目前仍是开放挑战。

---

## 八、强化学习与行为克隆的关系

### 8.1 BC 的本质局限

BC 本质是 SFT，只训练**训练分布内**的动作误差；但部署时分布来自**策略自己生成**——遇到训练未见的状态就会失效。

### 8.2 DAgger 系列算法

- **DAgger**：**离线**访问专家，请专家对策略实际访问到的状态打标
- **HG-DAgger**：**在线**访问专家，实时收集纠正动作
- **FreeDAgger**：进一步改进

核心目的都是**缩小训练分布与部署分布的差距**。

### 8.3 强化学习（RL）

让智能体**自己探索**——做对了给 reward，做错了惩罚——通过优化累积回报获得能力。

**Q-Learning** 核心公式：

$$Q(s, a) = \mathbb{E}\left[\sum_{t=0}^{\infty} \gamma^t r_{t+1} \mid s_0=s, a_0=a\right]$$

- 估计在状态 $s$ 下执行动作 $a$ 后，未来折扣累积奖励的期望
- Rollout 时选使 Q 最大的动作

**机器人领域常用算法**：**PPO**、**SAC**（均属 Actor-Critic 框架，与大模型 RLHF 中的 PPO 同源）。

---

## 九、WAM 整体技术栈小结

```
┌────────────────────────────────────────────────────────────┐
│                    课程知识地图                              │
├────────────────────────────────────────────────────────────┤
│  Understanding Expert                                      │
│    ↳ 多模态对齐：Qwen-VL、DINO、CLIP/SigLIP               │
│    ↳ Vision Transformer、Cross Attention                 │
├────────────────────────────────────────────────────────────┤
│  Action Expert                                            │
│    ↳ 简单 VLA：OpenVLA、π0                                │
│    ↳ 行为克隆：MSE 训练的问题                              │
│    ↳ 生成式动作：Diffusion Policy、Rectified Flow         │
├────────────────────────────────────────────────────────────┤
│  Video Expert                                              │
│    ↳ 视频生成模型（Wan）                                   │
│    ↳ 视频规划：UniPi、VBP（路线 2）                        │
├────────────────────────────────────────────────────────────┤
│  联合建模（WAM）：Motors、NeroVLA、DreamZero              │
│    ↳ Joint Attention + Mixture of Transformers           │
├────────────────────────────────────────────────────────────┤
│  Latent Action                                             │
│    ↳ Optical Flow（LAPA → Motors）、VA-VAE               │
├────────────────────────────────────────────────────────────┤
│  训练数据                                                  │
│    ↳ 数据金字塔、Web/Ego/合成/Target                      │
│    ↳ 跨本体：Open X-Embodiment                            │
├────────────────────────────────────────────────────────────┤
│  策略优化                                                  │
│    ↳ 行为克隆、DAgger/HG-DAgger                           │
│    ↳ RL：Q-Learning、PPO、SAC                             │
├────────────────────────────────────────────────────────────┤
│  仿真器                                                    │
│    ↳ RoboTwin 2.0 等                                      │
└────────────────────────────────────────────────────────────┘
```

---

## 十、入门路径建议（讲师推荐）

1. **选一个具体模型深入**：Motors、π0、NeroVLA 任选其一，搞清楚其完整运行机制
2. **从模型表现反推问题**：当前模型在哪些具身任务上还做不好？问题出在 understanding、action、视频建模还是数据？
3. **带着问题读对应文献**：每个缺陷都对应一个开放研究方向

---

## 十一、推荐阅读

### 基座模型与技术报告
- Motors、NeroVLA、DreamZero（WAM 系列）

### 建模与综述
- 具身智能综述类文献

### 多模态
- **Vision Transformer**、**DINO**、**CLIP**、**Qwen-VL**

### VLA 基座
- **OpenVLA**、**π0**（Physical Intelligence）

### Diffusion / Flow Matching
- **DDPM**、**DDIM**、**Classifier-Free Guidance (CFG)**
- **Latent Diffusion Model**、**Diffusion Transformer (DiT)**
- **Diffusion Policy**（重点理解其在策略建模中的角色）

### 视频策略与 Latent Action
- **UniPi**、**VBP**、**VDT**、**VDC**

### WAM 相关
- **Motors**、**NeroVLA**、**DreamZero**

### 模仿学习
- **DAgger**、**HG-DAgger**、**FreeDAgger**

### 机器人强化学习与模仿学习
- 经典 RL 教材 + **PPO**、**SAC**

### 数据与仿真器
- **Open X-Embodiment**（跨本体数据统一）
- **RoboTwin 2.0**（仿真器）
