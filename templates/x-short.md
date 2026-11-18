# X 内容与交接模板

模板仅提供字段与结构骨架，章节数量或线程帖数按当期论证实际需要决定，禁止为凑配额注水或机械等分。

## 1. X Articles 文章（默认，`mode: article`）

文件名：`content/social/MMDDHHMM-[纯中文主题]-X文章.md`

```markdown
---
title: [具体说明方法/结论并覆盖核心搜索词的文章标题]
author: 月明水清深
mode: article
status: draft
---

[导语：直接从真实场景、具体卡点与作者做法切入；不写顶层 # 一级标题，不用翻译腔或空泛悬念]

## [小节 1：具体动作或核心判断]

[自然中文短句展开：面向新手先说做什么、用什么、得到什么结果，再解释必要术语]

![单行具体图注：直接说明画面证据，不在图片下方再重复写第二遍相同图注](../../production/article/v01/assets/evidence-01.png)

## [小节 2：步骤、边界或迁移做法]

[保留作者原始数字、限定词、命令与专有名词；因果衔接自然]

[收束段：明确带走的结论或工作流做法]

参考入口：[官方文档或项目名](https://example.com)
```

配套封面与发布包交接信息（随稿登记或写入 `distribution/` 发布包）：

- **封面需求（交 `gbro-cover-design`）**：
  - 槽位与规格：`x-article`，画幅 **5:2**（预设 `2000×800`，左右 ≥`100px`、上下 ≥`64px` 安全边距，左下 `x=0–300, y=620–800` 标签遮挡区留纯背景）
  - 人像策略：`coverKind: "non_portrait"`（默认无人像，用主题具象道具 + 巨字对比表达；严禁裁切竖版真人封面替代）
  - 封面视觉大字建议：`[与文章 title 互补的短促主视觉大字]`
- **`moonlit-social-publisher` `platforms.x` 映射**：
  - `mode`: `"article"`，`title`、`body`（frontmatter 之后的正文）、`contentSource`（本 `.md` 路径）、`sourceSha256`（64 位小写 SHA-256）、`coverImage`（已验收 5:2 横图路径）、`coverKind`: `"non_portrait"`、`inlineImages`（按正文出现顺序排列的静态图路径数组）、`visibility`: `"public"`（不含 `posts`）
  - 交付边界：过 `guoshen`（`script` + `content`）门禁后写入 X Articles 原生草稿箱并回读，**默认终点 `draft`（不点 `Publish`、不为存草稿索要逐条发布批准）**。

---

## 2. 单条短帖（仅用户明确指定时，`mode: short`）

文件名：`content/social/MMDDHHMM-[纯中文主题]-X.md`

```markdown
---
author: 月明水清深
mode: short
selectionBasis: "[记录用户当次明确指定写单条短帖的原话或依据]"
status: draft
---

[首句直接点出具体工具/场景与实测结果或卡点]

[一个核心判断或具体做法；中文总长 ≤140 个可见字符，纯英文 ≤280 字符]

[按需项目链接或符合本期目标的 CTA；可选 0–2 个 #话题]

媒体（≤4 项，映射到 posts[0].media，不使用 coverImage/inlineImages）：
- [可选静态图或视频路径]
```

交付边界：经审核后交 `moonlit-social-publisher` 准备 `READY` 预览，**月明对本条当次明确批准后才外发**。

---

## 3. X 线程（仅用户明确指定时，`mode: thread`）

文件名：`content/social/MMDDHHMM-[纯中文主题]-X线程.md`

```markdown
---
author: 月明水清深
mode: thread
selectionBasis: "[记录用户当次明确指定写线程/thread的原话或依据]"
status: draft
---

## 1/N

[具体问题/实测结果 + 本串将展开的具体实操内容；禁用 🧵 与空泛震惊钩子]

媒体：
- [可选首帖配图路径]

## 2/N

[步骤或证据 1：每帖只承担一个信息任务，中文可见字符 ≤130]

媒体：[]

## 3/N

[步骤、边界判断或结论收束 + 可选链接；仅首帖或尾帖放 0–2 个 #话题]

媒体：
- [可选证据图路径]
```

`N ≥ 2`（按实际步骤自然分帖，不硬凑固定帖数；每帖 `media` ≤4 项，映射到 `posts[]`，不使用 `coverImage`/`inlineImages`）。经审核后交 `moonlit-social-publisher` 准备 `READY` 预览，**月明当次明确批准后才外发**。
