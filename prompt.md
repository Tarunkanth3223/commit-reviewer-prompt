分析当前 Git 仓库中[Target Author]在[Date Range]的工作表现，并生成一份详细的工作评估报告。

# Variables

- **Target Author**: `[这里填写你的 Git 用户名 或 邮箱]`
- **Date Range**: 2025-01-01 to 2025-12-31
- **Output File**: REPORT.md

# Instructions

## Step 0: Preparation (准备工作)

确保你在一个包含完整 Git 历史记录的本地仓库中工作

1. 如果用户没有提供 Target Author，请先运行以下命令列出前 20 名贡献者, 提供给用户选择.

```bash
git shortlog -sn --since="2025-01-01" --until="2025-12-31" | head -n 20
```

2. 请确认 Target Author 的 Git 签名（名字或邮箱），以确保数据准确。
3. 确认 Date Range, 如果用户没有提供，默认为 2025 年全年。

Attention: 听取用户的指示，避免擅自更改 Target Author 或 Date Range。

## Step 1: Data Extraction (执行命令)

请在当前终端执行 git log 命令来提取数据。
为了避免 Context Window 溢出，请不要一次性读取所有 diff。
请使用以下命令获取简明统计信息（如果仓库极大，请分季度提取）：

```bash
git log --author="Target Author" --since="2025-01-01" --until="2025-12-31" --pretty=format:"%h|%ad|%s" --date=short --no-merges --stat

```

_注意：如果不确定 Author 的具体 Git 签名，请先运行 `git shortlog -sn` 让我确认名字。_

## Step 2: Analysis (语义分析)

根据提取的 Commit 日志和统计数据，进行以下维度的深度分析：

1. **工作重心推断**：根据 Commit Message 的关键词（如 feat, fix, refactor, docs, chore），分析该开发者在不同时间段（Q1-Q4）的工作重点是什么？（例如：上半年主要在重构核心模块，下半年主要在开发新特性）。
2. **代码影响力**：根据修改的文件路径和行数变动，判断其工作是否涉及核心逻辑，还是主要在边缘模块或配置文件。
3. **工作习惯**：观察提交频率和时间分布，评价其提交粒度（是否原子化提交）和持续性。

## Step 3: Report Generation (写入文件)

将分析结果整理并写入 `REPORT.md`，报告必须包含以下章节（使用 Markdown 格式）：

### 2025 年度代码工作报告 - [Target Author]

#### 摘要

- 用简练的语言总结该开发者今年的主要贡献。
- 给出一个整体的“年度关键词”（例如：架构重构、业务攻坚、稳定性建设）。

#### 工作内容

- 列出 3-5 个由该开发者主导或深度参与的重要功能/模块（基于 Commit Message 推断）。
- _例如：完成了计费系统的重构，支持了多语言配置等。_

#### 季度工作重点

- **Q1**: [总结]
- **Q2**: [总结]
- **Q3**: [总结]
- **Q4**: [总结]

#### 代码与工程质量分析

- **提交活跃度**：(根据日志时间分布描述)
- **提交类型分布**：(估算 Feature/Fix/Refactor 的比例)
- **主要触达模块**：(列出修改最频繁的目录或文件类型)

#### 总结与展望

- 基于现有数据，对该开发者今年工作的客观评价。

---

你可以通过使用 subagent/task 等工具来并行的进行提取和分析工作来提高效率。

请现在开始执行 Step 1，并在获取数据后直接进行分析和文件写入，无需中间询问，除非找不到该 Author 的记录。
