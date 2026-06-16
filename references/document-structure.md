# 文档结构规范

在为软件项目建立论文材料目录、整理文献卡片、规划章节素材、放置图表和 LaTeX 产物时加载本文件。

## 总原则

- `docs/` 通常与 `src/` 平级，服务于论文写作和研究材料沉淀，不属于应用运行时目录。
- `docs/` 中的材料按论文章节和证据来源组织，而不是按代码包名机械同步。
- 一个文件应有清晰用途：文献卡片、章节素材、需求说明、设计说明、测试材料或最终成果。
- 新项目优先使用本规范；旧项目若已有顶层 `research/`、`project/`、`results/`，可继续读取其内容，但新增论文材料应逐步归并到 `docs/` 结构。

## 推荐目录

```text
docs/
  research/
    _shared/
    <topic>/
      README.md
      literature-index.md
      <source-card>.md
  intro/
    01-background-and-value.md
    02-research-status.md
    03-technology-introduction-and-selection.md
    04-main-work.md
  requirements/
    01-overview.md
    02-requirement-derivation.md
    03-functional-requirements.md
    04-non-functional-requirements.md
    diagrams/
  architecture/
    01-design-principles.md
    02-static-structure.md
    03-dynamic-structure.md
    04-data-management.md
    05-other-views.md
    detail/
    figure/
  test/
    01-test-plan.md
    02-test-cases.md
    03-test-records.md
    04-test-conclusion.md
  results/
    template-source/
    thesis/
    thesis-proposal/
    bib/
    figures/
    build-notes.md
```

## 目录职责

| 目录 | 职责 | 对应论文 |
| --- | --- | --- |
| `docs/research/` | 存放文献、标准、协议、技术资料和产品资料卡片，按主题分类 | 第 1 章、第 2 章、参考文献 |
| `docs/intro/` | 根据调研资料和项目技术栈整理选题依据、应用价值、研究现状、技术介绍、选型分析和本文主要工作 | 第 1 章、第 2 章 |
| `docs/requirements/` | 存放需求分析、需求导出、功能需求、非功能需求和用例图等材料 | 第 3 章 |
| `docs/architecture/` | 存放概要设计和详细设计材料，直接从项目代码、接口和运行机制总结 | 第 4 章、第 5 章 |
| `docs/architecture/detail/` | 存放核心子系统、核心模块、关键流程、算法或数据结构的详细设计 | 第 5 章 |
| `docs/architecture/figure/` | 存放架构相关 PlantUML 源文件和生成的 PNG 图 | 第 4 章、第 5 章 |
| `docs/test/` | 存放测试环境、方案、用例、记录、结果分析和测试结论 | 第 6 章 |
| `docs/results/` | 存放论文、开题报告等 LaTeX 成果、PDF、bib、最终图件和构建说明；若项目使用顶层成果目录，则对应 `results/thesis/` 和 `results/thesis-proposal/` | 最终交付物 |

## `docs/research/`

- 按主题分类，例如 `access-control/`、`messaging-protocols/`、`system-security/`。
- 以卡片为基本单元，一个卡片对应一篇文献、一份标准、一份技术报告、一项产品资料或一个关键资料源。
- 项目代码、依赖、配置或部署中已经采用的技术也应触发调研：为该技术本身、同类技术和可替代方案建立资料卡片或主题索引。
- 每个主题目录建议包含 `README.md` 说明主题边界，`literature-index.md` 维护卡片索引和引用状态。
- 文献卡片建议包含：基本信息、资料类型、核心观点、方法/系统、可引用论据、局限、不适合引用的内容、与论文可能关联的章节。
- 研究卡片只沉淀事实和可引用判断，不直接替代论文正文。正文写作时应重新组织论证链。

## `docs/intro/`

- `01-background-and-value.md`：整理选题背景、工程问题、应用价值和研究对象边界。
- `02-research-status.md`：基于 `docs/research/` 和项目技术栈梳理国内外研究现状和有关技术现状，按主题和时间脉络组织。
- `03-technology-introduction-and-selection.md`：整理相关技术介绍、技术选型依据、使用边界和替代方案比较；项目已采用的技术不能只按实现事实介绍，还要补充同类技术调研和选择理由。
- `04-main-work.md`：收束为本文主要工作，说明本文完成的系统设计、实现、集成和验证内容。
- 当某技术来源于项目实现时，写作链路应为：项目使用事实 -> 技术及同类方案调研 -> 研究现状或技术介绍 -> 选型分析 -> 本文设计边界。
- 每个文件应能独立支持论文对应小节，不依赖临时聊天记录或未落盘结论。

## `docs/requirements/`

- `01-overview.md`：描述业务流程、系统目标、角色、资源、运行场景和约束。
- `02-requirement-derivation.md`：说明需求来自哪些应用场景、研究发现、设计目标或利益相关者问题。
- `03-functional-requirements.md`：列出功能需求、需求编号、参与者、触发条件、主要流程和异常流程。
- `04-non-functional-requirements.md`：列出性能、安全、可靠性、可维护性、可扩展性等重点非功能需求，并给出验证方式。
- `diagrams/`：存放用例图、业务流程图、活动图、顺序图等需求分析图件的源文件和导出图。
- 需求应保持可追踪，不把详细模块设计提前写入需求，除非技术路线本身是硬约束。

## `docs/architecture/`

- `01-design-principles.md`：概述设计目标、原则和边界，例如分层、控制面/数据面分离、最小权限、故障隔离、可扩展点。
- `02-static-structure.md`：描述功能视图、逻辑视图、组件图、分层架构、部署视图等静态结构。
- `03-dynamic-structure.md`：描述核心交互流程、时序图、活动图、状态变化、异常流程和跨模块数据流。
- `04-data-management.md`：描述数据实体、E-R 模型、IE 实体关系图、表结构、缓存、配置、日志、数据一致性和生命周期。
- `05-other-views.md`：放置安全视图、协议适配视图、外部系统边界、错误处理或其他项目特色设计。
- `detail/`：一个核心子系统或模块一个文件，说明职责、接口、输入输出、状态归属、依赖、关键流程、异常处理和测试关联。
- `figure/`：存放架构设计相关图件，PlantUML 源文件使用 `.puml`，生成图使用 `.png`；同一图件源文件和导出图保持同名，例如 `overall-component-view.puml` 与 `overall-component-view.png`。
- 概要设计直接从项目代码、接口、部署和运行机制总结；不要写成泛化架构教材。

## `docs/test/`

- `01-test-plan.md`：说明测试对象、范围、环境、工具、方法、数据、拓扑和评价标准。
- `02-test-cases.md`：描述关键测试用例，覆盖功能需求、非功能需求和异常路径。
- `03-test-records.md`：保存执行记录、命令、截图、日志摘要、结果表格和失败分析。
- `04-test-conclusion.md`：总结测试目标是否完成、系统满足哪些需求、哪些边界尚未验证。
- 测试材料必须能支撑论文第 6 章的环境说明、用例设计、结果呈现和结论。

## `docs/results/`

- 存放最终或阶段性 LaTeX 成果，如 `thesis/`、`thesis-proposal/`、`bib/`、`figures/` 和构建说明。
- 如果项目采用顶层 `results/` 作为成果目录，则 `results/thesis/` 是论文成果目录，`results/thesis-proposal/` 是开题报告成果目录；这两个目录分别对应 `docs/results/thesis/` 和 `docs/results/thesis-proposal/` 的可复用结构。
- `template-source/` 可存放学校官方 LaTeX 模板的项目内归档副本或来源记录；不要把模板本体内联进 skill reference。
- `thesis/` 和 `thesis-proposal/` 可分别包含 `chapters/`、`figures/`、`build/`、`main.tex`、`ustcsetup.tex` 等模板相关文件。
- `results/thesis/` 和 `results/thesis-proposal/` 中生成或维护的 LaTeX 目录必须符合学校官方网站的 LaTeX 目录规范，确保入口文件、章节、参考文献、图片、样式文件和配置文件可被平台识别。
- 交付时以对应成果目录为根目录打包 zip：论文打包 `results/thesis/`，开题报告打包 `results/thesis-proposal/`。zip 上传学校官方网站后应能使用 XeLaTeX 编译生成 PDF。
- `bib/` 存放正式参考文献数据库或导出的参考文献列表。
- `figures/` 存放进入最终论文或开题报告的图件。源图可保留在语义目录中，最终导出版复制或链接到成果目录。
- `build-notes.md` 记录模板版本、入口文件、编译器 `XeLaTeX`、主要输出文件和格式问题处理记录。
- PDF 生成是可选验证步骤，不是必须交付动作。若生成 PDF 失败一次，例如缺少本地 LaTeX 环境、模板依赖或编译工具，不要重试，不要为生成 PDF 继续安装或修复本地环境。
- PDF 生成失败后，只维护可导入的 LaTeX 目录：确保入口 `.tex`、章节、参考文献、图件、样式/配置文件和构建说明齐全，供用户自行将对应成果目录打包上传到学校官网，并选择 XeLaTeX 生成 PDF。

## 命名和维护

- 文件名使用英文 kebab-case 和数字前缀，便于排序和跨平台处理。
- 章节素材文件优先按论文逻辑编号，不按创建日期编号；研究报告或调研过程记录可使用日期。
- 图件同时保留源文件和导出文件；架构相关 PlantUML 图件优先放在 `docs/architecture/figure/`，并保留 `.puml` 与 `.png`。
- 重要结论应能追溯到文献卡片、代码、设计文档、测试记录或最终结果。
- 不把聊天记录、一次性草稿、未核验资料直接放入最终成果目录；先整理为对应材料文件。

## 旧项目映射

旧项目可按以下方式迁移或理解：

| 旧位置 | 新规范位置 |
| --- | --- |
| `research/` | `docs/research/` |
| `project/intro/`、`project/tech-intro/` | `docs/intro/` |
| `project/requirements/` | `docs/requirements/` |
| `project/architecture/` | `docs/architecture/` |
| `project/detailed-design/` | `docs/architecture/detail/` |
| `results/materials/uml/architecture/` | `docs/architecture/figure/` |
| `project/testing/` | `docs/test/` |
| 根目录 `test/` 中的 LaTeX 模板 | `docs/results/template-source/`，或清理后进入 `results/thesis/` / `results/thesis-proposal/` |
| `results/results/` | `docs/results/` |
| `results/materials/` | 语义目录下的 `diagrams/` 或 `docs/results/figures/` |
