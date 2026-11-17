# lab-weekly-report

一个 Agent Skill：帮实验室成员把真实做过的工作和自己的学习收获，整理成给导师看的周报。用自然的中文表达，最终产出一份自包含、离线可打开的演示式 HTML，并按需嵌入事项配图和获准下载的原始资料。

核心原则是**不编造**：聊天记录、提交、文件、甘特图进度都只作为线索，必须由作者逐条确认状态与证据后才写进报告。

## 产出物

- 唯一交付：`YYYY-MM-DD-姓名-周报.html`。
- HTML 自包含：样式、交互、获准配图和选择供下载的原始文件均嵌入其中，可离线打开；不生成 Markdown、PDF、DOCX 或单独的图片/资料附件。
- 每次询问一次保存目录；文件已存在时不覆盖。

## 周报结构

- `本周工作概览`（仅在计数可靠时出现）
- `本周完成`：每项保留 `目标 / 具体动作 / 结果 / 证据`，再加入作者确认的 `学到了什么`
- `尝试但未完成 / 失败`：每项用 `尝试 / 原因或卡点 / 当前结论 / 下一步`
- `下周计划`：每项用 `目标 / 准备做的动作 / 预期结果`，确有依赖或风险时才加 `依赖或风险`
- `本周甘特图进度`：按报告周匹配任务，并标注 `已完成 / 进行中 / 未完成`

每个字段在 HTML 里都必须独立成块，不为了压页数而合并字段或缩小字号。采用 ACE 风格的 16:10 幻灯片、深石墨底色和红色强调；较长的工作项可以续到下一页，文字必须完整。

## 学习收获与配图

写作时会参考自然中文表达规则，删掉空泛的总结、宣传式措辞和机械的句式，保留真实细节与不确定性。

对已完成的事项，Agent 会先根据确认过的工作起草一段第一人称的「学到了什么」，再问你是否需要修改。你说可以才采用；有修改意见就继续调整到你满意。没有值得记录的收获，也可以确认后省略，不强行编造。保存前先在对话中展示完整报告草稿供确认。

如果某项工作配图能帮助理解，Agent 会说明用途，再让你选择「AI 生成」「自己提供」或「不需要」。选择提供图片就嵌入 HTML 并放在对应事项下方；选择 AI 生成则根据已确认的内容制作图片，示意图会明确标注。配图不替代证据。如果当前宿主没有图像生成功能，会说明限制，再由你选择提供图片或不配图。

## 文件说明

| 路径 | 作用 |
| --- | --- |
| `SKILL.md` | 主技能说明与完整工作流（Agent 读取的入口） |
| `references/html-output.md` | 演示式 HTML 视觉规范、单文件与离线要求、验收步骤 |
| `references/natural-writing.md` | 自然中文表达与学习收获的写作说明 |
| `references/report-images.md` | 配图判断、三种选择与 HTML 嵌入规则 |
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
请更新技能 lab-weekly-report：先检查安装方式和本地改动；如果是 Git 克隆且没有未提交修改，在它的目录里 git pull --ff-only；否则保留本地修改并说明如何更新。更新后确认 SKILL.md 和 references/ 完整。
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

技能会先确认作者、时间范围和项目范围，再列候选工作项让你逐条核对状态与证据，确认后才生成 HTML。所以第一次跑之前，最好准备好：这段时间的聊天记录（或让它自己检索）、甘特图，以及 HTML 想存到哪个目录。

## 适用范围

技能里的示例工具名（如 Codex 的会话读取接口）需要按宿主替换；若宿主无法读取聊天记录，技能会明确说明历史回顾不完整，而不是假装查过。

## License

[MIT](LICENSE) © 2026 chameleonn4
