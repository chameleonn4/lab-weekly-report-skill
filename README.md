# lab-weekly-report

一个 Agent Skill：帮实验室成员把一段时间内真实做过的工作，整理成给导师看的周报，最终产出内容完全一致的两份文件——Markdown 与 PDF。

核心原则是**不编造**：聊天记录、提交、文件、甘特图进度都只作为线索，必须由作者逐条确认状态与证据后才写进报告。

## 产出物

- `YYYY-MM-DD-姓名-周报.md`：可编辑的源文件，修改以它为准。
- `YYYY-MM-DD-姓名-周报.pdf`：由已确认的 Markdown 渲染，正文逐字一致，只额外包含右上角抬头与页脚页码。

不产出 DOCX。

## 周报结构

- `本周工作概览`（仅在计数可靠时出现）
- `本周完成`：每项用 `目标 / 具体动作 / 结果 / 证据` 四个字段
- `尝试但未完成 / 失败`：每项用 `尝试 / 原因或卡点 / 当前结论 / 下一步`
- `下周计划`：每项用 `目标 / 准备做的动作 / 预期结果`，确有依赖或风险时才加 `依赖或风险`
- `本周甘特图进度`：按报告周匹配任务，并标注 `已完成 / 进行中 / 未完成`

每个字段在 Markdown 和 PDF 里都必须独立成段，不为了压页数而合并字段或缩小字号。

## 文件说明

| 路径 | 作用 |
| --- | --- |
| `SKILL.md` | 主技能说明与完整工作流（Agent 读取的入口） |
| `references/pdf-output.md` | PDF 排版、页眉页脚规范与验收步骤 |
| `agents/openai.yaml` | 支持该格式的宿主的界面元数据 |
| `DESIGN_NOTES.md` | 面向技能作者的设计说明，日常使用时可忽略 |

## 安装

### 方式一：让 Agent 自己装（推荐）

不需要手动敲命令。把下面这句话发给你的 Agent —— DSH、Codex、Claude Code 都行：

```text
请把 https://github.com/chameleonn4/lab-weekly-report-skill 安装成技能：
克隆到你的技能目录，目录名用 lab-weekly-report，装完确认 SKILL.md 和 references/ 都在，然后告诉我它出现在技能列表里了。
```

Agent 会自己选对路径、克隆、检查结构。装完新开一个对话，问一句「你现在有哪些技能」，能看到 `lab-weekly-report` 就成功了。

已经装过、想升级时，同样交给 Agent：

```text
请更新技能 lab-weekly-report：在它的目录里 git pull，然后确认 SKILL.md 还是最新版本。
```

### 方式二：手动克隆

Agent 的技能目录约定如下，把仓库克隆进去，目录名用 `lab-weekly-report`：

| Agent | 技能目录 |
| --- | --- |
| DSH | `~/.dsh/skills/lab-weekly-report/` |
| Codex | `~/.codex/skills/lab-weekly-report/` |
| Claude Code | `~/.claude/skills/lab-weekly-report/` |

```bash
git clone https://github.com/chameleonn4/lab-weekly-report-skill.git ~/.dsh/skills/lab-weekly-report
```

Windows PowerShell：

```powershell
git clone https://github.com/chameleonn4/lab-weekly-report-skill.git "$env:USERPROFILE\.dsh\skills\lab-weekly-report"
```

只认目录结构，不认仓库名：只要目标目录里有 `SKILL.md`，且 `references/` 与它保持相对位置即可。

## 使用

装好之后有两种触发方式：

- 直接说「用 lab-weekly-report 写周报」。
- 或者只说「帮我写这周的周报」，支持隐式调用的宿主会自动加载它。

技能会先确认作者、时间范围和项目范围，再列候选工作项让你逐条核对状态与证据，确认后才生成 Markdown 和 PDF。所以第一次跑之前，最好准备好：这段时间的聊天记录（或让它自己检索）、甘特图、以及 PDF 想存到哪个目录。

## 适用范围

技能里的示例工具名（如 Codex 的会话读取接口）需要按宿主替换；若宿主无法读取聊天记录，技能会明确说明历史回顾不完整，而不是假装查过。

## License

[MIT](LICENSE) © 2026 chameleonn4
