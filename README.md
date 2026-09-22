![X 短帖与线程：一个洞察，或一条连续的论证](assets/readme/hero.png)

# 月明·X 短帖与线程

把一个洞察写成短帖，或把已有长文整理成连续论证的 X 线程，并安排每帖媒体。

## 你会得到什么

- 明确标注 short 或 thread 的文案
- 编号、顺序和媒体对应关系
- 可交给社交发布器的帖子材料

## 试着这样说

```text
用 moonlit-x-short。把这篇文章整理成 X 线程，每帖只承担一个信息任务，保留来源和证据，不反复重复结论。
```

## 安装与首次使用

将本仓库的完整目录交给支持本地 Skill 的 Agent 安装，保留 `SKILL.md` 与随附资源。已有同名版本时先检查差异；使用版本锁的工作区沿用自身升级机制。

让 Agent 安装：

```text
请安装这个 Skill：https://github.com/zzyong24/moonlit-x-short
```

也可通过 Skills CLI 安装：

```bash
npx skills add zzyong24/moonlit-x-short
```

## 配置与依赖

需要已有内容、当前品牌规范和目标语言。可从 moonlit-topic-engine 接收选题；平台操作由 moonlit-social-publisher 承接。写作本身无需配置 X 账号。

## 数据与使用边界

文本由当前 Agent 处理，只有后续发布才提交 X。线程默认建议 5–8 帖，最终字数以平台编辑器为准；仓库内的长度策略是创作约定，不能视作实时平台规则。

## 配套 Skill

[social-publisher](https://github.com/zzyong24/moonlit-social-publisher) · [topic-engine](https://github.com/zzyong24/moonlit-topic-engine)

## 详细说明

执行流程与资源导航见 [SKILL.md](SKILL.md)。安装检查不代表真实业务验收；需要外部服务、账号登录或付费生成的步骤，应在使用者自己的环境中验证。

---

月明水清深 · `moonlit-x-short`

首图为 AI 生成的品牌概念插画，不是工具截图或执行结果。
