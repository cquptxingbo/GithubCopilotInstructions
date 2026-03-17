---
applyTo: "**/*.test.*,**/*.spec.*,**/test/**,**/tests/**"
---

# 测试相关指令

编写测试代码时，请遵循以下规范：

## 测试结构

- 使用 AAA 模式（Arrange-Act-Assert）组织测试
- 每个测试用例只测试一个功能点
- 测试命名要清晰描述测试场景

## 测试覆盖

- 覆盖正常流程（Happy Path）
- 覆盖边界条件
- 覆盖异常情况和错误处理
- 避免测试实现细节，关注行为

## 测试质量

- 测试应该是独立的，不依赖其他测试的执行顺序
- 避免使用随机数据，使用固定的测试数据
- Mock 外部依赖（数据库、网络请求等）
- 测试运行速度要快

## 命名规范

```
// 推荐格式：should_<期望行为>_when_<条件>
test('should return empty array when input is empty', () => { ... })
test('should throw error when user not found', () => { ... })
```
