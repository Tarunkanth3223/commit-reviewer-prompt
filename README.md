# Commit Reviewer Prompt

一个用于分析 Git 仓库中开发者年度工作贡献的 AI Prompt。

## 使用方式

### 方式一：一步到位

直接将以下指令发送给你的 coding agent（Claude Code、Cursor、Cline 等）：

```
curl -s https://raw.githubusercontent.com/Disdjj/commit-reviewer-prompt/main/prompt.md 获取指令内容并执行
```

备用链接（国内可用）：

```
curl -s https://cdn.jsdelivr.net/gh/Disdjj/commit-reviewer-prompt@main/prompt.md 获取指令内容并执行
```

### 方式二：手动复制

1. 打开 [prompt.md](./prompt.md)
2. 复制全部内容
3. 粘贴给你的 coding agent 执行

## 功能

- 自动提取指定作者在指定时间范围内的 Git 提交记录
- 分析工作重心、代码影响力、工作习惯
- 生成结构化的年度工作报告（REPORT.md）

## License

MIT
