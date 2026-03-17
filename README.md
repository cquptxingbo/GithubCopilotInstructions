# GithubCopilotInstructions

用于保存 GitHub Copilot 的 instructions 指令文档。

## 说明

本仓库用于存储和管理 GitHub Copilot 的自定义指令文件，帮助团队统一 AI 编程助手的行为和输出风格。

## 文件结构

```
.github/
├── copilot-instructions.md          # 仓库级别的 Copilot 全局指令
└── instructions/                    # 特定场景的指令文件
    ├── code-review.instructions.md  # 代码审查指令
    ├── commit-message.instructions.md # 提交信息指令
    └── testing.instructions.md      # 测试相关指令
```

## 使用方式

### 仓库级别指令

`.github/copilot-instructions.md` 文件中的内容会自动应用到该仓库的所有 Copilot Chat 对话中。

### 特定场景指令

`.github/instructions/` 目录下的 `*.instructions.md` 文件可在特定场景下被引用，通过文件顶部的 `applyTo` 属性控制应用范围。

## 参考文档

- [GitHub Copilot 自定义指令文档](https://docs.github.com/en/copilot/customizing-copilot/adding-repository-custom-instructions-for-github-copilot)
