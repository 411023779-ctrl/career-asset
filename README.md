# 职业资产挖掘系统（Career Asset）

> 一个给 AI 编程助手用的结构化访谈 skill。帮有经验的职场人挖出被埋没的能力、把真实经历翻译成跨领域语言、生成中英双语的职业资产文档。

## 解决什么问题

大多数中高年限的职场人都被自己的职位名称困住了。一个管过 50+ 个项目、自己搭建了 AI 自动化流程的"景观设计师"，其实也是"复杂项目管理"+"AI 运营"——但简历上不会这么写。

这个 skill 让 AI 变成一个 HR 视角的访谈者，通过 8 个阶段的结构化对话：

- 把模糊的"负责项目管理"追问成有数字、可验证的成果
- 挖出简历上没写的隐藏资产（副业、接单、社群、自动化脚本）
- 打破职业标签，识别跨界能力组合
- 最终输出三份干净的中英双语文档，直接用于生成简历、搜索职位

## 适合谁用

**全行业通用。** 不管你是做金融、IT、法律、医疗、设计、运营还是其他行业，方法论是一样的——把"做过什么"变成"能卖什么"。AI 会根据你说的行业自动调整追问的方向和指标。

## 怎么装

把整个 `career-asset/` 文件夹复制到你项目里的 `.agents/skills/` 目录下。在 AI 编程助手里输入 `/career-asset` 即可启动。

支持的 AI 编程助手：Claude Code、Codex、Gemini CLI、OpenCode、Qwen、Copilot、Kimi 等兼容 [Agent Skills 标准](https://agentskills.io) 的工具。

## 跑完会生成什么

| 文件 | 语言 | 用途 |
|------|------|------|
| `career-asset-{姓名}-data-{日期}.md` | 英文（结构化字段） | AI 可读——喂给下游做 CV 生成、关键词搜索 |
| `career-asset-{姓名}-zh-{日期}.md` | 纯中文 | 人看的——个人画像、资产清单、方向建议、信息缺口 |
| `career-asset-{姓名}-en-{日期}.md` | 纯英文 | 人看的——可直接用于英文简历的专业描述、关键词 |

## 文件结构

```
career-asset/
├── SKILL.md                              ← 主 skill（8 阶段访谈流程）
├── references/
│   ├── hr-quality-rules.md               ← HR 质检规则（量化、禁词、6秒扫描、可追溯）
│   └── career-asset-template.md          ← 三文件输出模板
├── .gitignore                            ← 防止个人信息文件被提交
└── README.md                             ← 当前文件
```

## 设计原则

- **资产大于技能** — 问"你做过什么"，不问"你擅长什么"
- **没数字就没可信度** — HR 第一眼扫的就是量化结果
- **拆标签** — 每个职位背后藏着 3-5 个能迁移到其他行业的能力
- **不编造** — 所有声称必须能追溯到用户的原始表述
- **中英分离** — 中文用来深度自我梳理，英文用来市场输出，互不混杂
- **领域自适应** — AI 根据用户所在行业自动切换追问的语言和指标

## 怎么用

1. 在 AI 编程助手中输入 `/career-asset`
2. 按提示贴简历，或直接开始访谈
3. 每次回答后 AI 会自动做 HR 质检（追问不够具体的地方）
4. 五个访谈领域走完后，AI 自动生成三份文档
5. 随时可以说"暂停"，下次输入"继续"从中断处接着聊

## License

MIT

---

## Career Asset — Discovery & Exploration System (English)

A structured interview skill for AI coding assistants. Guides experienced professionals through an 8-phase conversation to surface quantified achievements, hidden skills, and cross-domain capabilities — then generates bilingual career asset documentation for CV generation and job search.

**Domain-agnostic.** Works for finance, IT, legal, healthcare, design, operations, and any other industry.

**Install:** Copy `career-asset/` into `.agents/skills/`. Invoke with `/career-asset`.

**Output:** Three files — structured data (AI-readable, EN), human-readable profile (中文), and CV-ready English summary.

MIT License.
