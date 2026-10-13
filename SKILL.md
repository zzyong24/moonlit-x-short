---
name: moonlit-x-short
description: 月明水清深 X 内容生成 sub-skill。支持单条短帖和主帖加连续自回复的 X 线程；多平台分发默认把公众号或小红书长度内容拆成 5–8 段，从 moonlit-content-engine 主入口调用。用户提到 X、Twitter、线程、thread、帖子串、分段评论或连续自回复时使用。
metadata:
  display_name: 月明·X 短文
  icon: icon.svg
  updated: "2026-10-04"
---

# 🌙 moonlit-x-short · X 内容 sub-skill

## When to use

- 主入口 `moonlit-content-engine` 引导做 X 分发时
- 用户单独要求 X 短帖、线程、thread、帖子串或连续自回复

## 共同输入与改写

按当前工程激活目录读取 `moonlit-content-engine/references/content-master-contract.md`，从作品 contentMaster 或用户已确认的事实简述与证据起稿，不强制先写公众号。为本次读者重新组织判断与证据顺序；不机械截段或填满帖子数量。已选 short/thread 范围优先，输出登记实际 inputs，知识回流遵守工作区规范。

## 产物位置

写入当前作品的 `content/social/`，不要写入 Skill 目录。

## 文件命名

```
MMDDHHMM-[纯中文主题]-X.md
MMDDHHMM-[纯中文主题]-X线程.md
```

**示例**：
```
2608261210-AI工具三个坑-X.md
```

## 模式选择

- `short`：单一洞察或用户明确要求单条时使用。
- `thread`：一源多形自动分发的默认模式；适合公众号或小红书长度内容。

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
- 输出明确编号、正文和媒体路径，供 `moonlit-social-publisher` 构建原生线程草稿

## 自检清单

- [ ] 已标明 `mode: short` 或 `mode: thread`
- [ ] short：≤140 字中文或 ≤280 字英文，且只有 1 个核心洞察
- [ ] thread：5–8 帖、顺序完整、每帖只承担一个信息任务
- [ ] hashtag 不重复刷屏
- [ ] 媒体与帖子一一对应，每帖不超过 4 个媒体项
- [ ] ID 一致：`月明水清深`

## 依赖

- `moonlit-brand-overlay.md`
- `moonlit-topic-engine`
- `content-creation-expert`：仅已安装且需要额外写作框架时使用；缺失时按本 Skill 的论证契约起稿，不阻塞基础能力。
- `moonlit-social-publisher`（发布准备、授权发布和结果核验）
