# Software Graduate Thesis Workflow

面向软件工程、软件专业硕士等场景的 Codex skill，用于辅助整理和撰写中文毕业论文相关材料。它将论文正文、开题报告、文献引用、研究卡片、PlantUML 图件、LaTeX 成果和 `docs/` 材料目录组织规则集中到一个可复用工作流中。

## 简介

本 skill 适用于以下任务：

- 规划和整理软件项目的论文材料目录。
- 撰写或修订论文正文、开题报告和章节素材。
- 规范参考文献、引用格式和研究卡片。
- 管理需求、架构、测试和最终成果材料。
- 处理 PlantUML 图件、LaTeX 结果目录和论文交付物放置规则。

主要文件：

- `SKILL.md`：skill 入口和任务路由规则。
- `references/document-structure.md`：论文材料目录结构规范。
- `references/thesis-format.md`：论文正文写作与格式规则。
- `references/proposal-format.md`：开题报告写作与格式规则。
- `references/citation-style.md`：引用和参考文献规范。
- `references/plantuml.md`：PlantUML 图件组织规则。
- `agents/openai.yaml`：Codex UI 展示元数据。

## 安装步骤

### 方式一：从 GitHub 克隆

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
git clone https://github.com/JackGaite/software-graduate-thesis-workflow.git \
  "${CODEX_HOME:-$HOME/.codex}/skills/software-graduate-thesis-workflow"
```

### 方式二：从本地目录复制

如果已经有本仓库的本地副本，可以复制到 Codex skills 目录：

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R /path/to/software-graduate-thesis-workflow \
  "${CODEX_HOME:-$HOME/.codex}/skills/software-graduate-thesis-workflow"
```

在当前机器上，本仓库路径为：

```bash
/Users/jack/thesis/software-graduate-thesis-workflow
```

### 启用和使用

安装后，重启 Codex 或开启新的 Codex 会话，使 skill 被重新发现。之后可以在请求中显式使用：

```text
Use $software-graduate-thesis-workflow to organize my thesis materials.
```

也可以用中文描述任务，例如：

```text
使用 software-graduate-thesis-workflow 帮我整理软件工程毕业论文的 docs 目录。
```
