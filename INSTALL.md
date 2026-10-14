# 安装超纲 OFFBRIEF

[简体中文](INSTALL.md) · [English](INSTALL.en.md)

当前技能版本：**1.3.0**。技能标识及安装目录名：**offbrief**。

超纲按照 [Agent Skills 目录规范](https://agentskills.io/specification) 组织，使用宿主的模型和工具。技能本身没有运行脚本，使用时无需另装 Python、Node.js 或单独配置模型 API。

## 方式一：让宿主安装

向支持 Skills 安装且能访问仓库的 AI 工具发送：

```text
帮我安装这个 Skill：https://github.com/ZzzShisi/offbrief
技能名 offbrief，SKILL.md 在仓库根目录。
按你实际识别的 Skills 目录安装，保留 references/ 和 assets/ 的相对位置。
如果已有同名技能，请先保留旧版备份，避免新旧版本同时加载。
安装后检查 metadata.version 为 1.3.0。
```

宿主如果只有导入技能包的功能，使用方式二。

## 方式二：安装技能 ZIP

下载 [OFFBRIEF_v1.3.0.zip](dist/OFFBRIEF_v1.3.0.zip)。专用包只含运行技能所需的文件与许可证。

### WorkBuddy

将专用 ZIP 提供给 WorkBuddy 的技能安装流程；支持对话安装的环境可以说：

```text
请安装附件中的超纲 OFFBRIEF 技能。
如果已经有旧版，先保留备份，再更新为 1.3.0。
安装后确认 offbrief/SKILL.md 和参考资料就位。
```

按该环境的机制刷新技能或新开会话，再进行下方的最短检查。WorkBuddy 的技能结构与官方市场说明见 [官方文档](https://open.workbuddy.cn/docs/skill)。不同安装入口的格式要求以实际界面为准。

### 压缩包布局

当前专用包结构：

```text
offbrief/
├── SKILL.md
├── references/
├── assets/
└── LICENSE
```

如果宿主明确要求 `SKILL.md` 位于 ZIP 根目录：解压后，将 `offbrief/` 文件夹里面的文件和子目录整体压缩，保留相对关系。

GitHub 的 **Code → Download ZIP** 下载的是整个仓库，还包括说明文档和展示图片。直接技能包导入优先使用本页链接的专用 ZIP。

## 方式三：Codex 本地目录安装

Codex 支持从用户目录 `~/.agents/skills` 或项目中的 `.agents/skills` 发现本地技能。依据见 [官方安装与技能发现说明](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills)。

### Windows PowerShell

需要 Git。目标目录已有同名技能时，先备份并处理旧版本；下面的克隆不会覆盖现有目录。

```powershell
git clone "https://github.com/ZzzShisi/offbrief" "$env:USERPROFILE\.agents\skills\offbrief"
```

### macOS / Linux

```bash
git clone "https://github.com/ZzzShisi/offbrief" "$HOME/.agents/skills/offbrief"
```

也可以下载并解压专用技能包，将整个 `offbrief/` 放入上述 Skills 目录。只想用于一个项目时，放入项目的 `.agents/skills/offbrief/`。

如果新技能没有出现，重启 Codex，再检查技能列表。Codex CLI 可明确使用 `$offbrief` 调用；自然匹配取决于描述、上下文和配置。

## 安装后最短检查

1. **看版本。** 确认安装文件的 `metadata.version` 是 `1.3.0`。
2. **问能力。** “超纲能帮我做什么？” 应涵盖找方向、推进任务、交付与成果复核。
3. **带任务试。** “我现在在做____，卡在____。换个方向，帮我想想。” 看看有没有与你的条件有关的新选择。
4. **试精确要求。** “只改这两个错字，不要建议。” 应只完成指定修改。

自然问法没有加载时，先明确指定「超纲」或 `offbrief`，再排查宿主发现机制。能力融入成果时，不一定出现额外的技能标题。

## 更新

从本仓库克隆安装且没有本地修改的用户，可以进入实际安装目录后运行：

```text
git pull --ff-only
```

若本地改过技能，先保留修改并查看差异，再决定怎样更新。用 ZIP 安装的用户下载新版后按原宿主流程替换，并保留旧版备份。

## 测试范围

1.3.0 的行为测试和自然发现观察来自本地 Codex 环境。已收到的 WorkBuddy 1.2.0 安装与试用反馈属于旧版本，不能作为所有 WorkBuddy 环境自动加载 1.3.0 的证明。具体记录见 [TESTING.md](docs/TESTING.md)。

官方文档核对日期：2026-10-14。
