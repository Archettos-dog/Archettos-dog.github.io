---
title: EBU5017 Paper A 参考答案
---

> **重要声明**：本文档依据官方 *Paper A Revision Guidance* 的 "key points to cover" 撰写，
> 采用课程标准答题法：**找规范 → 拆要件 → 逐要件(释义+套事实+小结) → 争议正反展开 → 分层结论 + 工程/治理含义**。
> 官方明确：评分奖励的是**把法律概念清晰、有选择地适用于事实**，而非背诵固定措辞。
> 故本文是**答题框架范例**，考场上应按时间(每题约 60 分钟、4 选 3)取舍裁剪，并结合最新案例灵活组织。
> 英文为考试作答语言，中文为复习对照。每问标注了对应的官方 key points。

---

# Question 1 — Deep Fakes & Disclosure (深度伪造与披露)

## Q1(a) 通用方法 (How to attack every sub-example)

**EN:** Article 3(60) yields three cumulative elements. Content is a deep fake **only if all three are met**:
- **(A) AI-generated or manipulated** image/audio/video content;
- **(B) Resembles** existing persons, objects, places, entities or events;
- **(C) Would *falsely* appear** to a person to be authentic or truthful.

The word "**falsely**" is decisive: **context, consent, disclosure, and audience expectations** determine whether element (C) is met. Not every synthetic or photorealistic output is a deep fake. These factors matter because the concept polices **deception**, not **synthesis**: consent addresses rights violation; disclosure neutralises the false-authenticity element by alerting viewers; context frames interpretation; audience expectation decides whether a reasonable viewer is actually misled.

**中:** 第 3(60) 条拆出三个**累积性**要件,缺一不可:(A) AI 生成或操纵的图像/音频/视频;(B) 与现实存在的人/物/地点/实体/事件**相似**;(C) 会**虚假地**让人误以为真实可信。"**虚假地**"一词是关键:**情境、同意、披露、观众预期**决定要件 C 是否成立。并非所有合成或照片级逼真内容都是深度伪造。这些因素之所以重要,是因为该概念规制的是**欺骗**而非**合成本身**:同意关乎权利侵犯;披露通过提醒观众消解"虚假真实外观";情境框定解读;观众预期决定理性观众是否真被误导。

---

### Q1(a)(i) AI 影视减龄/肖像重建 (Film de-aging)
> *Key points: 是否相似真实主体+是否误导；区分欺骗 vs 创意；context/consent 重要性。*

**EN:**
- **(A) Satisfied** — "manipulated" covers altering existing footage; de-aging a real actor via AI is clear manipulation.
- **(B) Satisfied** — the purpose is to depict a *specific, real* actor's recognisable likeness.
- **(C) Contested** — *For* deep fake: the image is photorealistic and technically indistinguishable from real footage. *Against (stronger)*: shown within an openly fictional film with audience awareness and (typically) actor consent, it does not *falsely* mislead anyone about reality. The deception the definition targets is absent.
- **Conclusion**: Consented, openly artistic de-aging is best seen as **AI-assisted creative work, not a deceptive deep fake** — though still within Article 50 transparency duties. It **would** become a deep fake if undisclosed, non-consensual (e.g., resurrecting a deceased actor without estate consent), or presented as a genuine record.
- **Engineering**: obtain/document consent; attach provenance metadata or watermark; disclose in credits to satisfy Article 50 without harming the artistic experience.

**中:**
- **(A) 满足**——"操纵"涵盖修改既有影像;用 AI 给真实演员减龄属明显操纵。
- **(B) 满足**——目的是呈现某个*特定真实*演员的可辨识肖像。
- **(C) 争议**——*支持*:影像照片级逼真、与真实影像无从区分。*反对(更有力)*:在公开虚构电影中放映、观众知情且(通常)演员已同意,并未*虚假地*误导任何人。定义针对的欺骗不存在。
- **结论**:经同意的、公开艺术性减龄宜定性为 **AI 辅助创作而非欺骗性深度伪造**——但仍受第 50 条透明度义务约束。若**未披露、未经同意**(如未经遗产继承人同意"复活"已故演员)或**被呈现为真实记录**,则构成深度伪造。
- **工程**:取得并留存同意;附溯源元数据/水印;片尾披露以满足第 50 条而不破坏艺术体验。

---

### Q1(a)(ii) 无同意的名人合成广告 (Non-consensual celebrity ads)
> *Key points: 误导风险最高；欺骗性用途的典型；consent 缺失是关键。*

**EN:**
- **(A) Satisfied** — celebrity likeness is AI-generated/manipulated.
- **(B) Satisfied** — resembles a real, identifiable celebrity/influencer.
- **(C) Clearly satisfied** — a synthetic endorsement is *designed* to make viewers believe the celebrity genuinely endorses the product; deception is the very purpose. **No** consent, **no** disclosure, **commercial** context → all point to "falsely appears truthful."
- **Conclusion**: This is a **paradigm deep fake** — all three elements met. It also engages personality/publicity rights and consumer-protection/advertising law (misleading endorsement). This is the clearest "deceptive use" end of the spectrum.
- **Engineering**: such content should not be produced without consent; platforms should detect, label, and remove; disclosure here cannot cure the underlying rights violation.

**中:**
- **(A) 满足**——名人肖像由 AI 生成/操纵。
- **(B) 满足**——相似于真实可辨识的名人/网红。
- **(C) 明显满足**——合成代言*本就意在*让观众相信名人真的代言;欺骗即其目的。**无**同意、**无**披露、**商业**情境 → 全部指向"虚假显得真实"。
- **结论**:这是**深度伪造的典型样态**,三要件全满足。还牵涉人格权/形象权与消费者保护/广告法(虚假代言)。这是光谱中最明确的"欺骗性用途"一端。
- **工程**:此类内容未经同意即不应制作;平台应检测、标注、下架;此处披露无法治愈底层的权利侵害。

---

### Q1(a)(iii) AI 虚拟偶像 Eternity (Fully synthetic avatars)
> *Key points: 并非每个合成虚拟形象都自动落入定义——这一问是该 key point 的核心战场。*

**EN:**
- **(A) Satisfied** — avatars are entirely AI-generated.
- **(B) NOT satisfied (decisive)** — Eternity's members are **fictional, non-existent** personas. The definition requires resemblance to *existing* persons/entities. Hyper-realism alone is not enough; they do not depict any real individual.
- **(C) Generally not satisfied** — presented openly as a virtual group; audiences know they are synthetic, so no *false* appearance of a real person.
- **Conclusion**: Eternity is **not a deep fake**, because element (B) fails — a critical demonstration that **not every hyper-real synthetic avatar falls within the definition**. The analysis would change if an avatar were built to resemble a *specific real* person.
- **Engineering**: still good practice to disclose AI-generated nature for transparency, but no deep-fake-specific liability arises.

**中:**
- **(A) 满足**——虚拟形象完全由 AI 生成。
- **(B) 不满足(决定性)**——Eternity 成员是**虚构、不存在**的角色。定义要求相似于*现实存在*之人/实体。仅仅超真实不够,她们不指向任何真实个人。
- **(C) 一般不满足**——公开作为虚拟团体呈现;观众知其为合成,故无"真实之人"的虚假外观。
- **结论**:Eternity **不是深度伪造**,因要件 B 不成立——这正是"**并非每个超真实虚拟形象都落入定义**"的关键例证。若某虚拟形象被造得相似于某*特定真实*之人,则结论改变。
- **工程**:为透明仍宜披露其 AI 生成属性,但不产生深度伪造的特定责任。

---

### Q1(a)(iv) Midjourney 等生成图工具 (Generative image tools)
> *Key points: 工具中立——取决于产出内容；区分明显合成 vs 欺骗性写实。*

**EN:**
- **(A) Satisfied** — outputs are AI-generated images.
- **(B) Context-dependent** — Midjourney can produce *either* fantastical content (no real subject → (B) fails) *or* images resembling **real, identifiable persons/events** (→ (B) satisfied). The tool is neutral; **the specific output decides**.
- **(C) Context-dependent** — a photorealistic fake image of a real politician at a real-seeming event "would falsely appear truthful"; an obviously stylised/fantasy image would not.
- **Conclusion**: Midjourney is **not inherently a deep-fake generator**. Whether a given output is a deep fake must be assessed **output-by-output** against (B) and (C). This shows the definition attaches to *content*, not *tool*.
- **Engineering**: provider should embed C2PA/provenance metadata and visible labels by default, given the tool's capacity to produce deceptive realistic images.

**中:**
- **(A) 满足**——产出为 AI 生成图像。
- **(B) 取决于情境**——Midjourney 既可生成奇幻内容(无真实主体→B 不成立),也可生成相似于**真实可辨识人物/事件**的图像(→B 成立)。工具中立,**由具体产出决定**。
- **(C) 取决于情境**——一张写实的、伪造某真实政客出现在貌似真实事件中的图"会虚假地显得真实";明显风格化/奇幻的图则不会。
- **结论**:Midjourney **本身并非深度伪造生成器**。某产出是否深度伪造须**逐张**对照 B、C 判断。这说明定义系于*内容*而非*工具*。
- **工程**:鉴于其生成欺骗性写实图的能力,提供方应默认嵌入 C2PA/溯源元数据与可见标注。

---

### Q1(a)(v) 实时 AI 语音合成 (Real-time voice / TTS)
> *Key points: 跨媒介适用(音频)；语音克隆 vs 通用合成音的区分。*

**EN:**
- **(A) Satisfied** — synthetic audio is AI-generated/manipulated (the definition expressly covers **audio**).
- **(B) Split** — *generic* synthetic voices (not cloned from any real person) do **not** resemble an existing person → (B) fails. *Cloned* voices replicating a **specific real individual's** voice → (B) satisfied.
- **(C) Split** — a cloned voice impersonating a real person in a deceptive call/message "falsely appears truthful"; a clearly artificial narration voice does not.
- **Conclusion**: Generic TTS is **not** a deep fake; **voice cloning of a real, identifiable person** can be — especially in fraud/impersonation contexts. Audio deep fakes are within scope just like video.
- **Engineering**: require consent for voice cloning; add audible disclaimers/inaudible watermarks; restrict real-person voice replication.

**中:**
- **(A) 满足**——合成音频由 AI 生成/操纵(定义明确涵盖**音频**)。
- **(B) 两分**——*通用*合成音(未克隆任何真人)**不**相似于现实之人→B 不成立;*克隆*某**特定真人**嗓音→B 成立。
- **(C) 两分**——在欺骗性通话/消息中冒充真人的克隆音"虚假地显得真实";明显人工的旁白音则不会。
- **结论**:通用 TTS **不是**深度伪造;**对真实可辨识之人的语音克隆**可以是——尤其在诈骗/冒充情境。音频深度伪造与视频一样落入范围。
- **工程**:语音克隆须取得同意;加可听免责声明/不可听水印;限制真人嗓音复制。

---

## Q1(b) 披露实践设计 (Designing disclosure) [50 marks]
> *Key points: 披露目的(透明/知情)；比较各方法优劣;时机为何重要;面向用户 vs 后端治理。*

**EN — Purpose first.** Disclosure exists to ensure **transparency, user awareness, and informed judgment** — so end-users can recognise artificial content *at the point of exposure*. Evaluate methods by four criteria: **clear, accessible, timely, and appropriate to the medium**.

**Comparison of methods (strengths vs limits):**

| Method | Strength | Limit |
|:---|:---|:---|
| **Visible labels / on-screen text** | Immediate, user-facing, no tools needed | Can be cropped, ignored, or removed; clutters content |
| **Watermarks (visible/invisible)** | Persist with the file; invisible ones resist cropping | Visible ones removable; invisible ones need detectors users lack |
| **Platform badges** ("AI-generated") | Consistent, platform-enforced, scalable | Only works on that platform; lost when content travels |
| **Metadata / provenance (C2PA)** | Tamper-evident, machine-verifiable, robust chain-of-origin | Invisible to ordinary users; stripped on re-upload; needs ecosystem support |
| **Audio/visual disclaimers** | Suited to medium (spoken notice, intro frame) | Easily skipped; weak for short-form/live content |

**Key distinction:** some methods are **strong for end-users** (visible labels, badges, audio disclaimers) while others mainly support **platform governance / back-end verification** (metadata, provenance). The **best design layers both** — human-readable disclosure *plus* machine-verifiable provenance.

**Why timing matters:** disclosure must appear **when users first encounter the content**, not buried in terms or revealed afterwards — otherwise the user has already been misled before learning the truth.

**Conclusion:** Effective disclosure is **layered, persistent, medium-appropriate, and delivered at the point of consumption**. A single method is insufficient; visible labels protect users now while provenance standards support enforcement and cross-platform durability.

**中 — 先讲目的。** 披露旨在确保**透明、用户知情、明智判断**——使终端用户能在*接触当下*识别人工内容。以四项标准评估方法:**清晰、可获取、及时、契合媒介**。

**方法对比(优劣):**

| 方法 | 优势 | 局限 |
|:---|:---|:---|
| **可见标签/屏幕文字** | 即时、面向用户、无需工具 | 可被裁剪/忽略/移除;干扰内容 |
| **水印(可见/不可见)** | 随文件保留;不可见水印抗裁剪 | 可见者可移除;不可见者需用户没有的检测器 |
| **平台徽章**("AI 生成") | 一致、平台强制、可规模化 | 仅在该平台有效;内容外流即失效 |
| **元数据/溯源(C2PA)** | 防篡改、机器可验、来源链稳健 | 普通用户看不见;重新上传被剥离;需生态支持 |
| **音视频免责声明** | 契合媒介(口播提示、片头帧) | 易被跳过;对短视频/直播弱 |

**关键区分:** 部分方法**对终端用户强**(可见标签、徽章、音频声明),部分主要支撑**平台治理/后端验证**(元数据、溯源)。**最佳设计两者分层叠加**——人类可读披露 + 机器可验溯源。

**时机为何重要:** 披露须在**用户首次接触内容时**出现,不能埋在条款里或事后揭示——否则用户在得知真相前已被误导。

**结论:** 有效披露应**分层、持久、契合媒介、于消费当下交付**。单一方法不足;可见标签当下保护用户,溯源标准支撑执法与跨平台持久性。

---

# Question 2 — AI Code Tool & Copyright (代码工具与版权)

## Q2(a) 中国版权保护什么 + 软件保护 (25 marks)
> *Key points: 保护表达非思想；软件可版权但难(混合创意与功能);思想/表达二分;结构性表达受保护但功能性元素不受。*

**EN:**
**Rule.** Under Chinese Copyright Law, copyright protects **original expression**, not **ideas, methods, processes, or functionality** (idea-expression dichotomy; cf. Software Protection Regulations Art 7, TRIPS Art 9). A work must be (i) in a literary/artistic/scientific domain, (ii) **original** (reflecting independent intellectual creation), and (iii) expressed in a perceivable form.

**Software's eligibility.** Software **can** qualify as a copyright work (computer programs are listed works). But it is **harder than most works because it mixes creativity with function**:
- **Protectable**: source code and object code (literal expression); original **structure, sequence and organisation** (non-literal expression) where creatively chosen.
- **NOT protectable**: underlying **algorithms, ideas, mathematical methods, operating processes**, and **functionally dictated elements** — where there is only one or very few ways to express a function, expression "merges" with idea and is unprotected.

**Conclusion.** Software receives copyright over its **original expressive elements**, but protection is **thinner** than for purely artistic works because functionally necessary code is excluded. *(Cases: 红色巴士 — originality through creative choices; 电话簿白页 — labour without creativity ≠ protectable.)*

**中:**
**规范。** 中国著作权法保护**独创性表达**,不保护**思想、方法、过程、功能**(思想/表达二分;参软件保护条例 A.7、TRIPS A.9)。作品须:(i) 属文学/艺术/科学领域;(ii) **独创**(体现独立智力创作);(iii) 以可感知形式表达。

**软件适格性。** 软件**可**作为作品(计算机程序为法定作品类型)。但它**比多数作品更难,因为混合了创意与功能**:
- **受保护**:源代码与目标代码(字面表达);经创造性选择的原创**结构、顺序与编排**(非字面表达)。
- **不受保护**:底层**算法、思想、数学方法、操作过程**及**功能决定的元素**——当某功能只有一种或极少表达方式时,表达与思想"合并"(merger),不受保护。

**结论。** 软件就其**原创表达元素**享有版权,但因功能必需的代码被排除,保护比纯艺术作品**更薄**。*(案例:红色巴士——创作选择带来独创性;电话簿白页——有劳动无创造性≠受保护。)*

---

## Q2(b) AI 训练是否侵权 + 中美对比 (50 marks)
> *Key points: 从复制入训练集起步(复制权);中国法不确定;大规模商用比私人学习/课堂更难证立;中国例外比美国 fair use 窄而具体;讨论目的/规模/市场影响;创新 vs 权利人利益的平衡;对比美国 fair use。*

**EN:**
**Issue.** Training copies millions of lines of code into a dataset → this **engages the reproduction right** (复制权). The question is whether a defence applies. **Separate input (training) from output (generation)** — this part concerns input.

**Chinese-law analysis (uncertain).**
- China has **no general fair-use clause** and **no specific AI-training exception**. Article 24 Copyright Law provides a **closed list** of limitations, mostly **non-commercial** (personal study, research, news, teaching), subject to the **two-step test** (A.21 Implementing Regulations): use must **not unreasonably prejudice the rightholder's legitimate interests** nor **conflict with normal exploitation** of the work.
- The Interim Measures for Generative AI (Art 7) require training data to come from **lawful sources** and not infringe IP — a general statement, not a safe harbour.
- **Large-scale commercial training is much harder to justify** than private study or classroom use: it is commercial, copies entire works, and may substitute for the original market. A startup commercialising a Comate-like tool therefore **cannot assume an automatic defence**.

**US contrast — fair use (§107), broader & flexible.** Four factors weighed case-by-case:
1. **Purpose/character** — is the use **transformative**? Commercial vs educational.
2. **Nature** of the copied work.
3. **Amount/substantiality** used.
4. **Market effect** (most important).
*Authors Guild v. Google* (full-book scanning held transformative, non-substitutive → fair use) supports AI-training defences; *NYT v. OpenAI* tests the limits where verbatim output and market harm appear.

**Balancing.** Innovation/競争 arguments (AI advances, learning ≈ human learning, only statistical patterns extracted) vs copyright-owner interests (unauthorised full reproduction; extraction of expressive features; market substitution).

**Conclusion.** Under **Chinese law the position is uncertain and the narrow A.24 list makes a defence hard** for commercial training; under **US law the flexible fair-use test offers more room but no guarantee**. The startup faces **real, non-trivial infringement risk** for the training stage.

**中:**
**争点。** 训练把数百万行代码复制入数据集 → **触发复制权**。问题在于有无抗辩。**须将输入(训练)与输出(生成)分开**——本问涉输入。

**中国法分析(不确定)。**
- 中国**无一般合理使用条款**,**无专门 AI 训练例外**。著作权法第 24 条是**封闭式**限制清单,多为**非商业**(个人学习、研究、新闻、教学),并受**两步检验**(实施条例 A.21)约束:不得**不合理损害权利人合法利益**,不得**影响作品正常使用**。
- 《生成式 AI 暂行办法》(A.7)要求训练数据来源**合法**、不侵犯 IP——属一般性表述,非安全港。
- **大规模商业训练远比私人学习或课堂使用难证立**:它是商业的、完整复制作品、可能替代原作市场。商业化类 Comate 工具的初创公司**不能假定有自动抗辩**。

**美国对比——fair use(§107),更宽更灵活。** 四要素个案权衡:① 目的/性质(是否**转换性**;商业 vs 教育);② 被用作品性质;③ 使用数量/比例;④ **市场影响**(最关键)。*Authors Guild v. Google*(整本扫描被判转换性、非替代→合理使用)支持 AI 训练抗辩;*NYT v. OpenAI* 在出现逐字输出与市场损害时检验其边界。

**平衡。** 创新/竞争论点(AI 进步、学习≈人类学习、仅抽取统计模式)vs 权利人利益(未授权完整复制、抽取表达性特征、市场替代)。

**结论。** 在**中国法下立场不确定,狭窄的 A.24 清单使商业训练难以抗辩**;在**美国法下灵活的 fair use 留有更多空间但无保证**。该初创在训练阶段面临**真实、不可忽视的侵权风险**。

---

## Q2(c) 输出与版权代码近乎相同 (25 marks)
> *Key points: 与训练问题分开;是否复制了受保护表达而非仅功能逻辑;开源许可条款也重要;立即+长期应对。*

**EN:**
**Issue (separate from training).** The question is whether the **output** is **substantially similar to protected expression**, not whether training was lawful.

**Legal risk analysis.**
- If the output reproduces the **literal code or original SSO** of the copyrighted function → likely **reproduction-right infringement** (cf. Ultraman case: AI output reproducing protected expression infringed reproduction + adaptation rights).
- If it only replicates **functional logic / an algorithm / an idea** (especially where there is only one efficient way to write it — merger) → **likely not** infringing.
- **Open-source licence terms also matter**: even "permissive" licences (MIT/Apache) require attribution; copyleft (GPL) may impose viral obligations. Reproducing licensed code without complying breaches the licence independently of copyright.
- **Liability spread**: both the **user** (who distributes the output) and the **company** (provider) may bear risk.

**Practical steps.**
- *Immediate*: reproduce and verify the report; quarantine/disable the offending output path; preserve logs.
- *Short term*: add **output filters / similarity detection** against known repositories; suppress verbatim regurgitation; surface licence/attribution notices.
- *Long term*: curate training data provenance; document lawful sources; implement a takedown/response process; consider licensing or opt-out mechanisms.

**Conclusion.** Risk turns on **whether protected expression (not mere function) was copied**; combine **legal assessment with concrete technical and process safeguards**.

**中:**
**争点(与训练分开)。** 问题是**输出**是否与**受保护表达实质性相似**,而非训练是否合法。

**法律风险分析。**
- 若输出复制了受版权函数的**字面代码或原创 SSO** → 很可能**侵犯复制权**(参奥特曼案:AI 输出复现受保护表达,侵复制权+改编权)。
- 若仅复制**功能逻辑/算法/思想**(尤其当只有一种高效写法时——合并原则)→ **很可能不**侵权。
- **开源许可条款也重要**:即便"宽松"许可(MIT/Apache)也要求署名;copyleft(GPL)可能带来传染性义务。复制受许可代码而不遵守,独立于版权另行违约。
- **责任分布**:**用户**(分发输出者)与**公司**(提供方)均可能担责。

**实务步骤。**
- *立即*:复现并核实报告;隔离/停用涉事输出路径;保全日志。
- *短期*:加**输出过滤/相似度检测**比对已知仓库;抑制逐字复吐;呈现许可/署名提示。
- *长期*:梳理训练数据来源;留存合法来源证据;建立下架/响应流程;考虑授权或退出机制。

**结论。** 风险取决于**是否复制了受保护表达(而非单纯功能)**;须**法律评估 + 具体技术与流程保障并用**。

---

# Question 3 — AI Harms & Evaluating AI Laws (AI 危害与立法评估)

## Q3(a) AI 法律要降低的主要危害 + 如何度量 (50 marks)
> *Key points: 几类不同危害;解释每类是什么+如何识别/度量;不要只罗列,要解释政府为何介入+如何证据化;真实案例;把法律干预连到可测量结果。*

**EN:** Identify **distinct categories**; for each give *what it is*, *why government intervenes*, *a real example*, and *how it can be measured*.

| Harm category | What it is / why intervene | Real example | How measured |
|:---|:---|:---|:---|
| **Safety** | Physical harm from autonomous/embodied AI | Autonomous-vehicle pedestrian misclassification (Uber Tempe) | Incident/accident rates, severity, recall data |
| **Discrimination / bias** | Systematic unfair treatment of groups | Facial recognition higher error rates for some groups; biased hiring tools | **Fairness metrics** (error-rate parity), audit findings |
| **Privacy** | Unlawful collection/use/re-identification | Clearview AI scraping 30bn images; Netflix Prize re-identification | Breach reports, DPA complaints, re-identification tests |
| **Deception** | Misleading users (deep fakes, false claims) | Non-consensual celebrity deep-fake ads | Complaint volumes, takedown rates, detection accuracy |
| **Security** | Manipulation/attack on AI systems | Data poisoning, prompt injection, model theft | Vulnerability counts, pen-test results, incident logs |
| **Societal / economic** | Misinformation, job displacement, power concentration | Recommender systems amplifying extreme content | Platform-level metrics, market-concentration indicators |

**Why measurement matters:** stronger answers **link legal intervention to measurable outcomes** — governments intervene where harm is **serious, hard for individuals to avoid, and evidenced** (cf. FTC unfairness test). Measurement turns vague concern into **incident rates, audit findings, fairness metrics, breach reports, and sector-specific indicators**.

**Conclusion:** AI laws target a **plural set of harms**, each requiring its own definition and metric; the strongest regulation ties duties to **evidence-based, measurable indicators** rather than abstract fears.

**中:** 识别**不同类别**;每类给出*是什么*、*政府为何介入*、*真实案例*、*如何度量*。

| 危害类别 | 是什么/为何介入 | 真实案例 | 如何度量 |
|:---|:---|:---|:---|
| **安全** | 自主/具身 AI 致物理伤害 | 自动驾驶行人误分类(Uber Tempe) | 事故率、严重度、召回数据 |
| **歧视/偏见** | 对群体的系统性不公 | 人脸识别对某些群体错误率更高;招聘工具偏见 | **公平性指标**(错误率均等)、审计发现 |
| **隐私** | 非法收集/使用/再识别 | Clearview 抓 300 亿图;Netflix Prize 再识别 | 泄露报告、DPA 投诉、再识别测试 |
| **欺骗** | 误导用户(深伪、虚假宣称) | 无同意名人深伪广告 | 投诉量、下架率、检测准确率 |
| **安全(security)** | 对 AI 系统的操纵/攻击 | 数据投毒、提示注入、模型窃取 | 漏洞数、渗透测试结果、事件日志 |
| **社会/经济** | 错误信息、就业冲击、权力集中 | 推荐系统放大极端内容 | 平台级指标、市场集中度指标 |

**度量为何重要:** 强答案**把法律干预连到可测量结果**——政府在危害**严重、个人难以避免、且有证据**处介入(参 FTC 不公平检验)。度量把模糊担忧转化为**事故率、审计发现、公平性指标、泄露报告与行业特定指标**。

**结论:** AI 法律针对**多元危害集合**,每类需各自的定义与度量;最强的监管把义务系于**基于证据、可度量的指标**,而非抽象恐惧。

---

## Q3(b) 政府如何评估 AI 法律成败 (50 marks)
> *Key points: 不只看法律是否存在,要看是否降低危害/可操作/仍允许有益创新;评估是持续而非一次性;指标;适应性机制(定期审查/仪表盘/沙盒);法律与经济的平衡。*

**EN:**
**Core thesis.** Success is **not** measured by whether laws *exist*, but by whether they **reduce harms, remain workable in practice, and still allow beneficial innovation**. Evaluation must be **ongoing, not one-off**.

**Indicators of success/failure:**
- **Harm reduction** — fewer incidents, breaches, biased outcomes (tie back to Q3(a) metrics).
- **Compliance & enforceability** — are duties clear and actually enforced? Penalty/enforcement data.
- **Clarity & workability** — can engineers translate rules into controls without disproportionate cost?
- **Trust** — public and market confidence in AI.
- **Innovation outcomes** — investment, startups, deployment *not* unduly chilled.

**Adaptive evaluation mechanisms:**
- **Periodic statutory reviews / sunset clauses** to update rules as technology shifts.
- **Dashboards & mandatory reporting** (incident registries, transparency reports).
- **Regulatory sandboxes** to test rules against real deployments before scaling.
- **Post-market monitoring** (as in the EU AI Act) feeding evidence back to regulators.

**Balance.** Avoid treating success as **purely legal** (laws passed) **or purely economic** (growth) — it is a **balance** between protection and innovation. Over-regulation chills beneficial AI; under-regulation leaves harms unaddressed.

**Conclusion.** Governments should evaluate AI laws through **continuous, multi-indicator, adaptive review** — measuring harm reduction *and* workability *and* innovation — rather than one-off or single-metric judgments.

**中:**
**核心论点。** 成败**不**以法律是否*存在*衡量,而看其是否**降低危害、在实践中可操作、且仍允许有益创新**。评估须**持续而非一次性**。

**成败指标:**
- **危害降低**——事故、泄露、偏见结果减少(回扣 Q3(a) 指标)。
- **合规与可执行性**——义务是否清晰并被实际执行?处罚/执法数据。
- **清晰与可操作**——工程师能否以不失衡的成本把规则转为控制?
- **信任**——公众与市场对 AI 的信心。
- **创新结果**——投资、初创、部署*未*被过度抑制。

**适应性评估机制:**
- **定期法定审查/日落条款**,随技术更新规则。
- **仪表盘与强制报告**(事件登记、透明度报告)。
- **监管沙盒**,在规模化前用真实部署检验规则。
- **上市后监测**(如 EU AI Act),把证据反馈给监管者。

**平衡。** 避免把成败视为**纯法律**(通过了法律)**或纯经济**(增长)——它是保护与创新间的**平衡**。过度监管抑制有益 AI;监管不足则危害无人处理。

**结论。** 政府应以**持续、多指标、适应性的审查**评估 AI 法律——同时度量危害降低、可操作性与创新——而非一次性或单一指标的判断。

---

# Question 4 — Cross-Border Health Data (跨境医疗数据)

> **全题主线:把欧盟数据与中国数据分开分析**(官方反复强调)。涉敏感健康数据(GDPR 特殊类别 / PIPL 敏感个人信息)。

## Q4(a) 集中存储到西班牙是否合法 (30 marks)
> *Key points: 区分 EU 与中国数据;识别特殊类别/敏感健康数据;合法性不仅靠同意,还需传输规则/研究保障/治理/安全;nuanced 结论。*

**EN:**
**Issue.** Can 130,000 chest CT scans (German + Chinese + Spanish) be centralised on a Spanish server? **The data must be split by origin because the legal regimes differ.**

**EU data (German + Spanish).**
- CT scans are **special-category health data** under GDPR Art 9 — processing prohibited unless an Art 9 condition applies (e.g., **explicit consent** or **scientific research** with Art 89 safeguards).
- **Germany → Spain is an intra-EU transfer** — **no cross-border transfer barrier** within the EEA; lawful if a processing basis + research safeguards (minimisation, pseudonymisation, security) exist.

**Chinese data (Fudan).**
- Health data is **sensitive personal information** under PIPL → needs **separate consent**, necessity, and impact assessment.
- **Cross-border transfer out of China is heavily restricted**: PIPL Arts 38–40 require a **CAC security assessment / certification / standard contract**, plus possible **data-localisation** constraints for important/health data (CSL, DSL). Patient consent **alone is not sufficient** — governance, security assessment, and approval are also required.

**Conclusion (nuanced).** Centralising **EU data** in Spain is **structurable lawfully** with a research basis and safeguards. Centralising **Chinese data** in Spain is **far more problematic** and likely **not permissible** without satisfying PIPL cross-border mechanisms and security assessment. So the plan is **partly feasible (EU) but legally unsafe as a whole (China)** — a simple "yes/no" is wrong.

**中:**
**争点。** 13 万张胸部 CT(德+中+西)能否集中到西班牙服务器?**须按来源拆分,因法律体制不同。**

**欧盟数据(德+西)。**
- CT 扫描为 GDPR 第 9 条**特殊类别健康数据**——禁止处理,除非满足第 9 条情形(如**明确同意**或带第 89 条保障的**科研**)。
- **德→西属欧盟内传输**——EEA 内**无跨境传输障碍**;若有处理基础+研究保障(最小化、假名化、安全)即合法。

**中国数据(复旦)。**
- 健康数据为 PIPL **敏感个人信息**→需**单独同意**、必要性与影响评估。
- **出境受严格限制**:PIPL 第 38–40 条要求**CAC 安全评估/认证/标准合同**,且重要/健康数据可能受**本地化**约束(CSL、DSL)。患者同意**本身不足**——还需治理、安全评估与审批。

**结论(细致)。** 将**欧盟数据**集中到西班牙**可合法构造**(研究基础+保障)。将**中国数据**集中到西班牙**问题大得多**,未满足 PIPL 出境机制与安全评估前**很可能不被允许**。故该计划**部分可行(欧盟)但整体法律上不安全(中国)**——简单"是/否"是错的。

---

## Q4(b) 笔记本失窃后的泄露通报义务 (25 marks)
> *Key points: 跨多法域;谁须通报/涉哪些机关/是否须告知个人/数据敏感度为何重要;时限;跨机构跨法域协调难题。*

**EN:**
**Issue.** Theft of a laptop with 5,000 scans (2,000 German, 2,000 Chinese, 1,000 Spanish), including ages, scan dates, hospital codes, and **patient initials** → a personal-data breach **affecting multiple jurisdictions**.

**GDPR (German + Spanish data).**
- **Art 33**: notify the competent **supervisory authority within 72 hours** of becoming aware, unless unlikely to risk rights/freedoms.
- **Art 34**: where **high risk** to individuals, **notify affected data subjects** without undue delay. Because this is **sensitive health data + identifiers**, the risk is high → **individual notification likely required**.
- Multiple DPAs may be involved (German + Spanish); a lead authority / cooperation mechanism applies.

**PIPL (Chinese data).**
- Breach of personal information → **notify the regulator (CAC) and affected individuals**; sensitivity raises the obligation. Timelines and content differ from GDPR.

**Why sensitivity matters & coordination.** Health data + re-identifiable metadata = **high-severity breach**, triggering individual notification across regimes. **Obligations differ between legal systems**, creating **coordination difficulty** across three institutions and authorities — who notifies whom, in what language, on which clock.

**Conclusion.** The consortium faces **parallel, non-identical notification duties** (EU 72-hour SA notice + high-risk individual notice; China CAC + individuals). The **multi-jurisdiction coordination** is itself a key challenge.

**中:**
**争点。** 失窃笔记本含 5,000 张扫描(2,000 德、2,000 中、1,000 西),含年龄、扫描日期、医院代码与**患者姓名缩写**→ **影响多法域**的个人数据泄露。

**GDPR(德+西数据)。**
- **第 33 条**:知悉后**72 小时内**通报主管**监管机构**,除非不太可能危及权利自由。
- **第 34 条**:对个人**高风险**时,**不无故迟延地通知受影响数据主体**。因属**敏感健康数据+标识符**,风险高→**很可能须个人通知**。
- 可能涉多个 DPA(德+西);适用主导机构/合作机制。

**PIPL(中国数据)。**
- 个人信息泄露→**通报监管者(CAC)并告知受影响个人**;敏感性提高义务。时限与内容与 GDPR 不同。

**敏感性为何重要 & 协调。** 健康数据+可再识别元数据=**高严重度泄露**,在各体制下触发个人通知。**各法律体系义务不同**,在三机构与多机关间造成**协调难题**——谁通知谁、用何语言、按哪个时钟。

**结论。** 联盟面临**并行但不相同的通报义务**(欧盟 72 小时监管机构通报+高风险个人通知;中国 CAC+个人)。**多法域协调**本身即核心挑战。

---

## Q4(c) "匿名化研究数据"抗辩评估 (25 marks)
> *Key points: 区分匿名化 vs 假名化/仍可再识别;若标识符/元数据/属性组合使再识别合理可能,则抗辩失败;研究身份不自动免除隐私义务;安全/泄露/传输规则仍适用;拒绝"研究数据在隐私法之外"的简单论断。*

**EN:**
**The argument fails.** Carefully distinguish:

- **Anonymised** = re-identification **not reasonably possible** by any means → falls outside personal-data law.
- **Pseudonymised / still re-identifiable** = identifiers replaced but re-identification **remains reasonably possible** → **still personal data**, still covered.

**Application to the facts.** The scans include **patient ages, scan dates, hospital codes, and patient initials in metadata**. These are **identifiers and quasi-identifiers**; in combination they make **re-identification reasonably possible**. This is **at best pseudonymised, not anonymised**. *(Netflix Prize: a few "anonymous" ratings + dates uniquely re-identified individuals — sparse attributes suffice.)*

**Why the broader claim fails.**
- **Research status does not automatically remove privacy obligations** — GDPR Art 89 / PIPL still impose safeguards on research.
- **Security, breach-response, and transfer rules still apply** regardless of the "research" label.
- The data is **health data** (special category / sensitive) — among the most protected.

**Conclusion.** The "anonymised research data" argument is **rejected**: the data is **re-identifiable personal (indeed sensitive) data**, so privacy law **fully applies**, including the breach-notification and transfer obligations above. Research does **not** sit outside privacy law.

**中:**
**该抗辩不成立。** 仔细区分:
- **匿名化** = 以任何手段**再识别不合理可能**→ 脱离个人数据法。
- **假名化/仍可再识别** = 标识符被替换但再识别**仍合理可能**→ **仍是个人数据**,仍受约束。

**套事实。** 扫描含**患者年龄、扫描日期、医院代码、元数据中的姓名缩写**。这些是**标识符与准标识符**;组合起来使**再识别合理可能**。这**至多是假名化,而非匿名化**。*(Netflix Prize:少量"匿名"评分+日期即唯一再识别个人——稀疏属性即足够。)*

**为何更广的论断失败。**
- **研究身份不自动免除隐私义务**——GDPR 第 89 条/PIPL 仍对研究施加保障。
- 不论"研究"标签,**安全、泄露响应、传输规则仍适用**。
- 该数据是**健康数据**(特殊类别/敏感)——受保护程度最高之列。

**结论。** "匿名化研究数据"抗辩**被否定**:数据是**可再识别的个人(且敏感)数据**,隐私法**完全适用**,包括上述泄露通报与传输义务。研究**不**在隐私法之外。

---

## Q4(d) 推荐合法合规的替代数据架构 (20 marks)
> *Key points: 解释为何集中所有原始数据有问题;替代架构如何在降低传输风险的同时保留科研协作;技术架构仍须治理/审批/安全支撑。*

**EN:**
**Why centralising raw data is problematic.** Pooling all raw scans in Spain forces **cross-border transfer of Chinese sensitive health data** (PIPL restrictions), concentrates breach risk in one location, and violates **data minimisation/localisation**.

**Recommended architecture — Federated Learning (decentralised).**
- **The model travels to the data, not the data to the model.** Each institution trains locally on its own scans; **only model parameters/gradients** (not raw CT images) are exchanged and aggregated.
- This protects **input privacy**, keeps Chinese data **in China** (respecting localisation + cross-border rules), and still produces a model trained across all three populations — **achieving the scientific goal** of cross-population generalisation.
- **Add differential privacy** to the shared updates to prevent reconstruction of individual records (output privacy); **secure aggregation** to protect parameters in transit.

**Governance still required.** Technical architecture **alone is not enough** — it must be supported by: research **ethics approvals**, **data-processing/transfer agreements**, **access controls and logging**, breach-response plans, and security assessments in each jurisdiction.

**Conclusion.** A **federated + differential-privacy** design preserves the collaboration's scientific value while **minimising cross-border transfer and localisation risk**, provided it is **wrapped in proper governance, approvals, and security controls**.

**中:**
**为何集中原始数据有问题。** 把所有原始扫描汇集到西班牙,迫使**中国敏感健康数据跨境传输**(PIPL 限制),将泄露风险集中于一地,违反**数据最小化/本地化**。

**推荐架构——联邦学习(去中心化)。**
- **模型到数据所在地,而非数据到模型。** 各机构在本地用自有扫描训练;**仅交换并聚合模型参数/梯度**(非原始 CT 图像)。
- 这保护**输入隐私**,使中国数据**留在中国**(尊重本地化+出境规则),仍能产出跨三类人群训练的模型——**达成**跨人群泛化的科研目标。
- **对共享更新加差分隐私**,防止重建个体记录(输出隐私);**安全聚合**保护传输中的参数。

**仍需治理。** 技术架构**本身不够**——须配以:研究**伦理审批**、**数据处理/传输协议**、**访问控制与日志**、泄露响应计划,及各法域的安全评估。

**结论。** **联邦学习 + 差分隐私**设计既保留协作的科研价值,又**最小化跨境传输与本地化风险**,前提是**以适当的治理、审批与安全控制加以包裹**。

---

# 附录 · 考场速记 (Exam-day reminders)

- **4 选 3,每题约 60 分钟** —— 选最有把握的三题,留时间写结论。
- **每问的骨架不能省**:规范 → 要件 → 套事实 → (争议)正反 → 分层结论 → 工程/治理含义。
- **比较题**:点出差异**根本原因**(中国重国家安全 / 欧盟重基本权利 / 美国重市场)。
- **场景题(Q2/Q4)**:务必**分开分析**(输入 vs 输出;欧盟数据 vs 中国数据)。
- **结论要 nuanced**,避免简单 yes/no;**挂案例**当弹药。
- 时间紧时优先保:**A/B/C 三要件主线 + 争议要件正反 + 分层结论**,可砍掉次要类比与重复释义。

---

*本参考答案依据 EBU5017 Paper A 官方 Revision Guidance 的 key points 撰写,结合课程三周知识点与案例。为框架范例,非唯一标准答案;考场应按时间与具体题目灵活取舍。*
