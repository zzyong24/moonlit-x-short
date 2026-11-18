---
name: moonlit-x-short
description: "月明水清深 X 内容写作 sub-skill：X Articles；明确要求时也写短帖或线程。默认撰写完整 X Articles 文章（配 5:2 默认无人像封面需求交 gbro-cover-design，经审核后交 moonlit-social-publisher 写入原生草稿箱）；仅在用户当次明确指定单条短帖或连续自回复线程时才生成 short 或 thread，禁止把多平台分发或长文擅自拆成线程。用户提到写 X 文章、发 X、Twitter、X 短帖、线程、thread 或帖子串时使用。不负责封面生图、公众号长文、小红书图文或浏览器实际发帖。"
metadata:
  display_name: 月明·X 文章与帖子
  icon: icon.svg
  updated: "2026-11-17"
---

# 🌙 moonlit-x-short · X 文章与帖子

## When to use

- 主入口 `moonlit-content-engine` 分发到 X，或用户说“写 X 文章 / 同步 X / 发到 X”（**默认 `mode: article`**，产出完整 X Articles 文稿）
- 用户**当次明确指定**写单条 X 短帖（`mode: short`）或连续自回复线程 / thread / 帖子串（`mode: thread`）

不适用：公众号长文（`moonlit-wechat-article`）、小红书图文（`moonlit-xiaohongshu`）、封面实际出图（`gbro-cover-design`）、浏览器写草稿或发帖执行（`moonlit-social-publisher`）。

## 共同输入与语言底线

1. **输入与信达雅**：按当前工程激活目录读取 `moonlit-content-engine/references/content-master-contract.md` 与 `moonlit-content-engine/references/editorial-contract.md`（若工作区含 `maintenance/spoken-style-profile.json` 一并参考），从作品 `contentMaster` 或用户已确认的口述、事实与证据起稿，不强制先写公众号。忠实保留作者判断、经历、数字、限定词、命令与专有名词，不自行审查观点或插入“仅供参考 / 以实际为准 / 待核验”等规避语。
2. **母语直述，严禁翻译腔**：用自然中文短句直接陈述问题、动作与结果；面向新手讲技术时，先说明这一步做什么、需要什么、得到什么结果，再解释必要术语。吸收英文推文或外文文档素材时必须消化后重述，**严禁英文直译腔**（禁止“这是一条关于……的线程”“让我们深入剖析 / 探索”“这彻底改变了游戏规则”“不可思议的是”及冗长被动定语从句），也不强塞作者原稿没有的网络口癖。
3. **严禁空泛钩子与AI套话**：开篇直接落具体工具/场景、真实卡点或可验证结果；**禁止空泛悬念与营销套话**（禁止 `🧵`、`99%的人都不知道/做错了`、`花了我X小时整理的保姆级干货`、`建议先码后看`、`以下是我学到的N件事：`、`综上所述`、`总而言之`、`值得注意的是`）。

## 模式选择（默认 Articles，严禁擅自拆帖）

- **`article`（默认主模式）**：“发 X / 写 X / 全平台分发 / 同步 X”一律使用 `article`，产出完整 X Articles 文章，不添加帖子编号、不拆成连续自回复。发布前若发现当前账号无 X Articles 权限，由下游如实报告阻塞缺口，**严禁降级拆成 `thread` 或普通长帖替代**。
- **`short`（显式指定）**：仅在用户本轮明确要求“单条推文 / X 短帖”或明确指定只发单一短判断时使用，记录当次指定依据。
- **`thread`（显式指定）**：仅在用户本轮明确要求“线程 / thread / 帖子串 / 连续自回复”时使用，记录当次指定依据。

## 产物位置与命名

写入当前作品的 `content/social/`（严禁写入 Skill 目录）：

```text
MMDDHHMM-[纯中文主题]-X文章.md
MMDDHHMM-[纯中文主题]-X.md
MMDDHHMM-[纯中文主题]-X线程.md
```

示例：`11150010-云端产物与上下文协作-X文章.md`。文稿与交接结构参考 [templates/x-short.md](templates/x-short.md)。

## 各模式内容规范

### 1. `article` 内容规范（默认）

- **结构与标题**：标题写入 frontmatter `title`（同步映射发布包 `platforms.x.title`）；**Markdown 正文首行不重复写 `# 一级标题`**，直接从具体场景/卡点导语起笔，章节统一使用 `##` 二级标题（供下游转为原生 H2），结尾给出清晰收束与可选参考链接。
- **正文配图与图注防重**：每张证据图嵌在解释它的段落附近，统一用 `![单行具体图注](相对或工作区路径)`，与发布包有序静态图数组 `inlineImages` 一一对应；**严禁在图片语法紧邻上下行再重复写一遍相同图注或斜体说明**（防原生编辑器出现双份图注），不残留“据母稿绘制 / 开篇核心问题”等内部编排词。
- **5:2 默认无人像封面交接（交 `gbro-cover-design`）**：
  - 统一对接 `gbro-cover-design` 的 `x-article` 槽位：目标画幅 **5:2**（团队制作预设 `2000×800`，左右 ≥`100px`、上下 ≥`64px` 安全边距，左下 `x=0–300, y=620–800` 标签遮挡区只留纯背景）。
  - **默认无人像（`coverKind: "non_portrait"`）**：不传本人照片，用具象主题道具、巨字与空间对比表达（除非月明当期另有明确人像要求）；**严禁拿 3:4 竖版真人视频封面临时裁切、拉伸或补边替代**。
  - **大字与标题互补**：随稿附上建议的「封面视觉大字」（短促抓注意）与「文章 `title`」（说明具体方法并自然覆盖搜索关键词），两者互补、不机械照抄，且不伪造正文未支持的数据或界面。

### 2. `short` 内容规范（仅明确指定时）

- **字数硬限**：中文正文 **≤140 个可见字符**，纯英文 **≤280 字符**（匹配下游预检上限）。
- **单核推进**：第 1 句直接点出具体对象、真实卡点或实测结果；中间只讲 **1 个核心判断或做法**，不硬塞多条清单。
- **CTA 与标签**：CTA 仅在符合本期目标时添加（开源项目直接给仓库链接，不默认引导扣词或加微信）；hashtag 按需 `0–2` 个，不刷屏。

### 3. `thread` 内容规范（仅明确指定时）

- **自然分帖与字数**：按实际论证或操作步骤分帖（**≥2 帖**，常见 `3–7` 帖，**不硬凑固定帖数配额**）；每帖中文可见字符 **≤130**（纯英文 **≤280**），最终以 X 编辑器计数为准。
- **单帖职责**：`1/N` 直接写出具体问题/结果与本串将展开的具体内容（禁止只抛空悬念不给实质信息）；中间每帖只承担一个步骤、证据或边界判断；尾帖收束结论或给项目链接。
- **防重复与标签**：保持连续推进，不把同一句钩子、结论或 CTA 改写重复多次；全线程仅在首帖或尾帖放 `0–2` 个 hashtag。

## 发布包交接契约（对接 `moonlit-social-publisher`）

只允许使用 X 主账号（大号，禁止 `xiaohao`）。文稿确认后先按工程 `publish-review.md` 完成 `guoshen` 审核（`script` 文本审 + 上传前 `content` 完整包审），再按模式交接：

- **`mode: "article"` 交接字段与默认草稿终点**：
  - `platforms.x` 必填：`mode: "article"`、`title`、`body`（不含顶层 `# H1`）、`.md` `contentSource`、匹配的 64 位小写 `sourceSha256`、已验收 5:2 横版 `coverImage`、`coverKind: "non_portrait"`、有序静态图 `inlineImages`（无配图填 `[]`）、`visibility: "public"`；**严禁包含 `posts` 字段**。
  - **默认终点是原生草稿箱（`draft`）**：由 `moonlit-social-publisher` 写入 `https://x.com/compose/articles` 原生草稿并回读正文、H2、配图与 5:2 头图后即完成，把草稿链接报给月明亲自发表；**不点击 `Publish`，也不为存草稿向月明索要逐条发布批准**（仅当月明后续专门要求代点发表某篇时才转入 `final` 与批准分支）。
- **`mode: "short"` / `"thread"` 交接字段与逐条批准**：
  - `platforms.x` 必填：`mode: "short"`（`posts` 恰好 1 条）或 `mode: "thread"`（`posts` 至少 2 条），每条为 `{ "text": "...", "media": [...] }`（每帖静态图/视频 ≤4 项）；**严禁包含 `coverImage` 或 `inlineImages` 字段**。
  - 交 `moonlit-social-publisher` 准备到 `READY` 展示含目标账号的单条最终预览，**获月明对这一条当次明确批准后才执行外发**，发后回报链接。

## 交付自检（可观测核验）

- [ ] `mode` 已标明：`article` 为默认；若为 `short` 或 `thread`，已记录用户本轮明确指定依据
- [ ] 语言核验：零英文推文直译腔、零 `🧵` 与空泛震惊钩子、零 AI 总结套话；原稿数字、限定词与技术专有名词 100% 守恒
- [ ] `article` 核验：正文无顶层 `# H1`，章节用 `##`；正文 `![图注](路径)` 与 `inlineImages` 顺序一致且无相邻重复图注；已附 `gbro-cover-design` `x-article` 5:2（`2000×800`）`non_portrait` 封面需求及与 `title` 互补的封面大字；不含 `posts`，标注默认终点为原生草稿 `draft`
- [ ] `short` / `thread` 核验：`short` 1 帖且中文 ≤140 字（英文 ≤280 字）；`thread` ≥2 帖且每帖中文 ≤130 字（英文 ≤280 字）；每帖 `media` ≤4 项，不含 `coverImage`/`inlineImages`，hashtag ≤2 个且不重复刷屏；标注需月明逐条批准后外发
- [ ] 作者署名为 `月明水清深`，目标账号非 `xiaohao`，`contentSource` 与 `sourceSha256` 可复算匹配

## 依赖与协作边界

- `moonlit-content-engine`（读取 `content-master-contract.md`、`editorial-contract.md`、`publish-review.md`）
- `moonlit-de-ai-perception`（成稿语言去 AI 味审读；缺失时按本 Skill 语言底线独立完成）
- `gbro-cover-design`（生产 `x-article` 5:2 默认无人像横版头图；本 Skill 只交文案与槽位需求，不出图）
- `moonlit-social-publisher`（校验发布包、`article` 写原生草稿箱回读记 `draft`、`short`/`thread` 获逐条批准后外发）
