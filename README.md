# AI_Compute_Subsidies

本仓库用于整理和推进一项关于 **国家人工智能创新应用先导区（NAIZ）、AI 算力补贴、地方同质化竞争与创新质量** 的实证研究。

根目录 `README.md` 是仓库入口，主要回答三件事：

1. 这个项目研究什么；
2. 合作者应该从哪里开始读；
3. 当前文件结构和协作边界是什么。

具体的研究设计、变量定义、空间计量方案和待核验事项，请阅读 [notes/organized/README.md](notes/organized/README.md)。该文件是 notes 阅读入口，不承担仓库说明功能。

## 当前研究定位

本文的主政策冲击是 **工信部国家人工智能创新应用先导区（NAIZ）**，不是科技部“国家新一代人工智能创新发展试验区”。两套政策需要分别编码，科技部 AI 试验区目前被视为最高风险混淆政策。

当前研究主线：

- **H1 主效应**：NAIZ 是否提升城市 AI 创新质量；
- **H2 核心机制**：地方算力补贴和相似 AI 政策竞争是否削弱 NAIZ 的创新质量效应；
- **H3 扩展检验**：NAIZ 是否对周边非 NAIZ 城市产生非 AI 部门 TFP 溢出，且该溢出是否被相似政策竞争削弱。

空间计量目前采用更保守的设计：以 **SLX / 空间暴露 DID** 为主，`SDM` 仅作为稳健性或补充检验。

## 两个 README 的分工

| 文件 | 用途 | 适合读者 |
|---|---|---|
| [README.md](README.md) | 仓库首页、协作入口、目录说明、当前状态 | 第一次打开仓库的合作者 |
| [notes/organized/README.md](notes/organized/README.md) | 整理版 notes 的阅读顺序和材料索引 | 准备细读研究设计的人 |

根目录 README 不写成论文正文，也不重复所有 notes 细节；它只保留足够的项目上下文，并把详细内容链接到正式 notes。

## 推荐阅读路径

第一次了解项目，建议按以下顺序：

1. 先读本文件，确认项目主题、文件结构和协作方式；
2. 再读 [notes/organized/README.md](notes/organized/README.md)，进入整理版 notes；
3. 重点阅读：
   - [01_项目定位.md](notes/organized/01_项目定位.md)
   - [04_实证假设.md](notes/organized/04_实证假设.md)
   - [05_变量与数据.md](notes/organized/05_变量与数据.md)
   - [06_空间计量方案.md](notes/organized/06_空间计量方案.md)
   - [07_待办与未确认事项.md](notes/organized/07_待办与未确认事项.md)
4. 需要追溯原始材料时，再回到 [notes/raw](notes/raw) 和 [notes/review_archive](notes/review_archive)。

## 目录结构

```text
.
├── README.md                 # 仓库入口和协作说明
├── AGENTS.md                 # Codex / AI 协作规范
├── code/                     # 后续实证代码
├── data/                     # 数据目录，不提交原始大数据
├── notes/
│   ├── raw/                  # 原始 notes，保留原文件名和内容
│   ├── organized/            # 正式整理版 notes
│   └── review_archive/       # GPT / Claude / Codex review 原文与融合建议
├── outputs/                  # 表格、图形、临时输出
├── paper/                    # 论文正文与 LaTeX 源文件
└── references/               # 文献、BibTeX、政策文件索引
```

## 当前材料状态

- `notes/raw/`：保留原始 notes，作为追溯依据。
- `notes/organized/`：当前正式阅读主线，包含 `01-08` 和目录 README。
- `notes/review_archive/`：保存 GPT、Claude、Codex 的 review 和空间计量融合材料，作为修订依据，不作为正式阅读主线。
- `code/`、`data/`、`outputs/`、`paper/`、`references/`：为后续实证、论文写作和文献管理预留。

## 协作原则

- 不直接改写 `notes/raw/`，除非明确需要补充原始材料。
- 对外发送材料时，优先发送 `notes/organized/` 和根目录 README。
- 正式写作或引用前，需要回到原始政策文件、原始文献和数据库口径核验。
- 政策事实、城市映射、变量定义和模型设定的最新判断，以 `notes/organized/` 中的正式 notes 为准。

## 最高优先级待确认事项

详细清单见 [07_待办与未确认事项.md](notes/organized/07_待办与未确认事项.md)。当前最高优先级包括：

- NAIZ 各批次公文原文、批复时间和城市 panel 映射；
- 科技部 AI 试验区完整名单和批复时间；
- 各城市算力券、模型券、智算中心政策文本；
- FTZ 片区所在城市与城市级编码；
- CPC/IPC AI 专利识别口径、前向引用窗口和右侧截尾处理；
- 城市经纬度、距离矩阵、空间暴露变量和 donut / placebo 检验设计。

## 当前阶段

截至 2026-06-05，本仓库处于 **研究设计与 notes 整理阶段**。尚未进入正式数据清洗、实证代码编写和论文正文写作阶段。
