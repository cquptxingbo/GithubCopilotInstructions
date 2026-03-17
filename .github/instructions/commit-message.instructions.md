---
applyTo: "**"
---

# 提交信息指令

生成 Git 提交信息时，请遵循以下规范：

## 格式

使用 [Conventional Commits](https://www.conventionalcommits.org/) 规范：

```
<类型>[可选的作用域]: <描述>

[可选的正文]

[可选的脚注]
```

## 类型

- `feat`: 新功能
- `fix`: Bug 修复
- `docs`: 文档变更
- `style`: 代码格式调整（不影响功能）
- `refactor`: 代码重构（既不是新功能也不是 Bug 修复）
- `test`: 添加或修改测试
- `chore`: 构建过程或辅助工具的变动
- `perf`: 性能优化

## 要求

- 描述使用祈使句，简洁明了
- 第一行不超过 72 个字符
- 如有必要，在正文中详细说明变更原因和内容
- 关联相关 Issue 时使用 `Closes #xxx` 或 `Fixes #xxx`
