<div align="center">

# Gradpilot

### 面向 agents 与 CLI 的可复用留学申请策略 skill

把分散的申请者信息整理成可直接决策的建议，用于背景评估、选校分层、SOP 定位、简历包装与申请节奏规划。

> 为真实申请决策而写，不提供空泛鼓励。

![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)
![Skill Type](https://img.shields.io/badge/Type-Strategy%20Skill-7c3aed)
![Use Case](https://img.shields.io/badge/Use%20Case-Graduate%20Applications-2563eb)
![Host](https://img.shields.io/badge/Host-Agent%20%7C%20CLI-0f766e)

[中文](./README.md) · [English](./README.en.md)

[安装](#quick-install-zh) · [为什么选择](#why-gradpilot-zh) · [能力范围](#features-zh) · [适用场景](#use-cases-zh) · [兼容性](#compatibility-zh) · [示例](#examples-zh)

</div>

<a id="quick-install-zh"></a>

## 快速安装

### Codex

```bash
git clone git@github.com:Maropion03/gradpilot.git ~/.codex/skills/gradpilot
```

```powershell
git clone git@github.com:Maropion03/gradpilot.git $HOME\.codex\skills\gradpilot
```

### Claude Code

```bash
git clone git@github.com:Maropion03/gradpilot.git ~/.claude/skills/gradpilot
```

```powershell
git clone git@github.com:Maropion03/gradpilot.git $HOME\.claude\skills\gradpilot
```

默认把 `SKILL.md` 当作主指令文件使用；只有在需要评分框架或输出模板时，再加载 `references/`。

<details>
<summary>其他 host 安装路径</summary>

克隆到自定义目标目录：

```bash
git clone git@github.com:Maropion03/gradpilot.git <TARGET>
```

建议目标路径：

| Host | macOS / Linux | Windows PowerShell |
|---|---|---|
| Codex | `~/.codex/skills/gradpilot` | `$HOME\.codex\skills\gradpilot` |
| Claude Code | `~/.claude/skills/gradpilot` | `$HOME\.claude\skills\gradpilot` |
| 通用自定义 host | 你的 host 本地 skills / prompts 目录 | 你的 host 本地 skills / prompts 目录 |
| 独立 prompt bundle | 任意可复用 prompt 目录 | 任意可复用 prompt 目录 |

如果你不想克隆整个仓库，也可以只下载核心文件：

```bash
mkdir -p gradpilot
cd gradpilot
curl -O https://raw.githubusercontent.com/Maropion03/gradpilot/main/SKILL.md
mkdir -p references
curl -o references/evaluation-rubric.md https://raw.githubusercontent.com/Maropion03/gradpilot/main/references/evaluation-rubric.md
curl -o references/output-templates.md https://raw.githubusercontent.com/Maropion03/gradpilot/main/references/output-templates.md
```

</details>

<a id="why-gradpilot-zh"></a>

## 为什么选择 Gradpilot

大多数留学申请建议的问题，不是信息少，而是太泛、太虚，或者乐观得不值得信。Gradpilot 的目标是把建议变成真正能拿来判断下一步的东西：

- 它会区分事实和推断，不会把脆弱假设包装成结论。
- 它把选校看成 portfolio decision，而不是只列一个“梦校清单”。
- 它关注叙事是否可信，而不只是把简历字面润色得更好看。
- 它会给出用于规划的概率分层，但不会假装自己能预测录取。
- 它会明确告诉用户下一步该补什么，而不只是给好听的话。

目标很直接：让 agent 或 CLI 在处理留学申请问题时，输出更现实、更可执行、更适合决策的建议。

<a id="features-zh"></a>

## Gradpilot 能做什么

- 评估硕士或博士申请背景
- 构建冲刺 / 主申 / 保底选校列表
- 比较项目与国家路径
- 设计 SOP / PS 叙事方向
- 调整简历内容与项目适配度
- 规划申请时间线与优先级

<a id="use-cases-zh"></a>

## 何时使用

当用户需要留学申请相关的判断、优先级建议或策略规划时，就适合使用 Gradpilot。

典型请求：

- “帮我评估一下我申请 MSBA 的背景。”
- “帮我做一个美国 / 英国选校名单。”
- “比较一下这几个项目，告诉我哪个 fit 更真实。”
- “帮我定位 SOP 主线和简历叙事。”
- “这个申请季我最先该补什么？”

## 不适用场景

Gradpilot 不是以下问题的主工作流：

- 签证或移民材料填写
- DS-160 一类操作型表单
- 奖学金系统逐项填报
- 文书逐句润色
- 与留学申请无关的泛职业咨询

## 最佳输入信息

最少建议提供：

- 简历、CV 或一段背景摘要
- 目标学位与目标方向

强烈建议补充：

- 当前学校、专业、GPA 制度与排名百分位
- 语言成绩与标准化考试成绩
- 实习、科研、项目、论文、奖项
- 目标国家、申请年份与预算敏感度
- 毕业后的职业目标

如果关键信息缺失，Gradpilot 仍然可以先给建议，但应该明确标注为 rough planning estimate。

## 输出模式

Gradpilot 不会把所有问题都硬套成同一种格式，而是会根据用户真实需求选择输出轨道：

- 选校建议
- 项目比较
- SOP / PS 策略
- 简历定位
- 申请时间线
- 混合策略 review

默认输出结构：

1. 申请者概况
2. 核心判断
3. 结果成品
4. 下一步行动
5. 缺失信息（仅在信息不足明显影响判断时保留）

<a id="compatibility-zh"></a>

## 宿主兼容性

### 通用 agent 或 CLI

把 `SKILL.md` 当作行为主文件即可。宿主至少需要能做到：

1. 加载 skill 指令
2. 把指令注入到 agent 上下文
3. 在需要更强结构化判断时，额外暴露参考文件

如果你的环境支持 slash commands、prompt library 或 named skills，可以把 Gradpilot 注册成一个专门处理留学申请策略的 skill。

### Codex / Claude Code 这类本地 skill 宿主

建议使用：

- `SKILL.md` 作为行为契约
- `agents/openai.yaml` 作为展示元信息
- `references/` 作为可选参考材料

其中：

- `Codex`
  - macOS / Linux: `~/.codex/skills/gradpilot`
  - Windows PowerShell: `$HOME\.codex\skills\gradpilot`
- `Claude Code`
  - macOS / Linux: `~/.claude/skills/gradpilot`
  - Windows PowerShell: `$HOME\.claude\skills\gradpilot`

### 其他 agent 框架

如果宿主没有原生 skill 机制，这个仓库也可以当作：

- 可复用 system prompt
- prompt template bundle
- 针对留学申请任务的 instruction preset

关键不是宿主名字，而是尽量保留 `SKILL.md` 里的 workflow 和 communication rules。

## 仓库结构

- `SKILL.md` - 核心说明与工作流
- `references/evaluation-rubric.md` - 结构化评估维度
- `references/output-templates.md` - 紧凑输出模板
- `agents/openai.yaml` - 支持该能力的宿主可选展示元数据

<a id="examples-zh"></a>

## 快速使用示例

### 卡片 1：先做选校分层

适合用户已经有基本背景，想快速拿到冲刺 / 主申 / 保底结构。

```text
请用 Gradpilot 帮我评估 2027 年申请 [国家] 硕士项目的背景。

我的背景：
- 学校 / 专业：
- GPA / 排名：
- 语言 / 标化成绩：
- 实习 / 科研 / 项目：

目标：
- 方向：
- 国家：
- 偏好：均衡选校

请输出：
1. applicant snapshot
2. 冲刺 / 主申 / 保底选校列表
3. 主要风险点
4. 下一步最该补的内容
```

### 卡片 2：先定 SOP 主线

适合背景不差，但叙事方向还不稳定，想先找最可信的故事线。

```text
请用 Gradpilot 帮我梳理 [项目方向] 的 SOP 策略。

我的背景：
- 当前专业：
- 关键经历：
- 为什么想转向 / 继续这个方向：
- 职业目标：

请重点回答：
1. 最强叙事主线
2. 哪些弱点需要重构表达
3. 应该重点强调哪些证据
4. 这套故事最适合申请哪些项目
```

### 卡片 3：先比较国家或项目路径

适合已经缩小到几个方向，想判断哪个选择更匹配自己。

```text
请用 Gradpilot 比较下面几个选项和我的匹配度：
- 选项 A：
- 选项 B：
- 选项 C：

我的背景：
- 学校 / 专业：
- GPA：
- 经历：
- 职业目标：

请按这些维度判断：
1. fit
2. 录取难度
3. ROI
4. 毕业后路径
5. 主要 tradeoff
```

## 自定义说明

Gradpilot 默认是偏克制、偏保守的：

- 默认使用中文，除非用户明确要求别的语言
- 录取概率只是方向性规划区间，不是假装精确预测
- 目标明显不现实的时候要直接校准
- 必须区分事实与推断

如果你要把它改造成某个市场、某类项目或某个机构场景专用的版本，建议保留这套判断框架，只本地化项目逻辑、示例和术语。
