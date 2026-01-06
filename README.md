# Commit Reviewer Prompt

一个用于分析 Git 仓库中开发者年度工作贡献的 AI Prompt。

## 快速使用

在你的 coding agent（Claude Code、Cursor、Cline 等）中执行：

```
curl -s https://raw.githubusercontent.com/Disdjj/commit-reviewer-prompt/main/prompt.md
```

然后根据返回的指令进行操作。

### 一键指令

直接复制以下内容发送给你的 coding agent：

```
请获取并执行 https://raw.githubusercontent.com/Disdjj/commit-reviewer-prompt/main/prompt.md 中的指令
```

## 功能

- 自动提取指定作者在指定时间范围内的 Git 提交记录
- 分析工作重心、代码影响力、工作习惯
- 生成结构化的年度工作报告（REPORT.md）

## 输出示例

生成的报告包含：

- **摘要**：年度关键词与主要贡献
- **工作内容**：主导或深度参与的重要功能/模块
- **季度工作重点**：Q1-Q4 各季度工作重心
- **代码与工程质量分析**：提交活跃度、类型分布、触达模块
- **总结与展望**

## License

MIT
