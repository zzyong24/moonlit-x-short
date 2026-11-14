---
name: moonlit-x-short
description: "月明水清深 X 内容生成 sub-skill。默认承接完整 X Articles 文章；单条短帖和连续自回复线程仅在用户明确指定时使用，禁止把多平台分发自动拆成线程，可从 moonlit-content-engine 主入口调用。用户提到 X、Twitter、线程、thread、帖子串、分段评论或连续自回复时使用。本 Skill 只写X文章/短帖/线程内容，审核通过后交给发布工具 moonlit-social-publisher（月明逐条批准后才发）；不用于公众号长文或小红书图文。"
metadata:
  display_name: 月明·X 文章与帖子
  icon: icon.svg
  updated: "2026-10-04"
---

# 🌙 moonlit-x-short · X 内容 sub-skill

## When to use

- 主入口 `moonlit-content-engine` 引导做 X 分发时（默认article）
- 用户单独要求 X 短帖、线程、thread、帖子串或连续自回复

## 共同输入与改写

按当前工程激活目录读取 `moonlit-content-engine/references/content-master-contract.md`，从作品 contentMaster 或用户已确认的事实简述与证据起稿，不强制先写公众号。为本次读者重新组织判断与证据顺序；不机械截段或填满帖子数量。已选 article/short/thread 范围优先，输出登记实际 inputs，知识回流遵守工作区规范。

## 产物位置

写入当前作品的 `content/social/`，不要写入 Skill 目录。

## 文件命名

```
MMDDHHMM-[纯中文主题]-X.md
MMDDHHMM-[纯中文主题]-X线程.md
MMDDHHMM-[纯中文主题]-X文章.md
```

**示例**：
```
2608261210-AI工具三个坑-X.md
```

## 模式选择

- `short`：单一洞察或用户明确要求单条时使用。
- `article`：多平台分发及“X发文章”的默认模式；完整文章进入 X Articles，使用非真人封面，复用已确认母稿及证据，不拆成帖子。先核当前账号Articles可用性；不可用时报告具体权限缺口，不改发线程或长帖。
- `thread`：仅用户明确要求线程、thread、帖子串或连续自回复时使用。

## article 内容规范

- 使用完整标题、导语、章节和结论，保留已确认论证与来源；不添加帖子编号或拆成自回复。
- 证据图片嵌在解释它的正文附近；记录正文图顺序及源稿hash。
- 封面为非真人主题概念/证据图；实际画幅按Articles入口核定，不裁真人视频封面替代。
- 输出完整Markdown与素材清单，由social-publisher的Articles路径核验上传；正文、图片、封面和原生声明都审核后才可提交。

## short 内容规范

- **总长 ≤140 字**（中文）或 **≤280 字**（英文）
- **开头 1 句话钩子**（前 10 字必须有冲击力）
- **中间 1 个核心洞察**（不贪多）
- **CTA 可选**：符合本期目标才添加；开源分享可直接给项目链接，不默认扣词或加微信。
- **hashtag** 2-3 个

## thread 内容规范

- 5–8 帖；每帖中文正文建议 ≤130 个可见字符，最终以 X 编辑器计数为准
- 第 1 帖：结果钩子 + 阅读承诺
- 中间帖：每帖只讲一个步骤、证据或判断，可把相关图片分配到对应帖
- 最后 1 帖：结论或下一步，CTA 可无；全线程只在主帖或尾帖放 1–2 个 hashtag
- 保持连续论证，不把同一句钩子、总结或 CTA 改写后重复多次
- 输出明确编号、正文和媒体路径，供 `moonlit-social-publisher` 构建原生线程草稿；**审核通过后交给发布工具**：先给月明看最终预览，月明对这一条明确批准后才由发布工具发帖，发布后回报链接

## 自检清单

- [ ] 已标明 `mode: article`、`mode: short` 或 `mode: thread`；article保留完整文章、非真人封面并进入原生Articles编辑器；例外有本轮明确选择依据
- [ ] short：≤140 字中文或 ≤280 字英文，且只有 1 个核心洞察
- [ ] thread：5–8 帖、顺序完整、每帖只承担一个信息任务
- [ ] hashtag 不重复刷屏
- [ ] 媒体与帖子一一对应，每帖不超过 4 个媒体项
- [ ] ID 一致：`月明水清深`
- [ ] 交付物标注「待月明审核」；只有月明对这一条明确批准后才交发布工具

## 依赖

- `moonlit-brand-overlay.md`
- `moonlit-topic-engine`
- `content-creation-expert`：仅已安装且需要额外写作框架时使用；缺失时按本 Skill 的论证契约起稿，不阻塞基础能力。
- `moonlit-social-publisher`（审核通过后发布：逐条预览、月明逐条批准、发布后回报链接）
