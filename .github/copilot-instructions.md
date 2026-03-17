# GitHub Copilot Instructions

## Basic Principles
- Use concise, clear code; avoid unnecessary complexity.
- Prioritize code readability and maintainability.
- Follow the existing code style and conventions of the project.
- Add necessary comments, but avoid over-commenting obvious code.

## Comment & Language Policy
- All code comments: English.
- All explanatory / chat responses: Simplified Chinese.

## Code Style
- Variable and function names should be meaningful and clearly express their purpose.
- Functions should follow the Single Responsibility Principle; avoid overly long functions.
- Prefer existing libraries and tools; avoid reinventing the wheel.
- Handle errors thoroughly; do not ignore exceptions.

## Control Statement Style
- Always use braces for single-line bodies (if / for / while / do / switch labels).
  Example:
  if (condition)
  {
      DoWork();
  }

## C++ Class Declaration Style
- Prefer declaring and initializing class members in the header file.
- Use in-class member initializers (C++11 and later) instead of initializing in the constructor body.
- Keep class declarations self-contained in headers whenever possible.
  Example:
  ```cpp
  // MyClass.h
  class MyClass
  {
  public:
      MyClass() = default;
      MyClass(int value) : m_value(value) {}

      int GetValue() const { return m_value; }

  private:
      int m_value = 0;           // in-class default initializer
      bool m_isActive = false;   // in-class default initializer
      std::string m_name = ""; // in-class default initializer
  };
  ```

## Code Region Organization
- Use `#pragma region` / `#pragma endregion` to group code by **functional theme** (what the members do), not by syntax category.
- Region names should describe the responsibility or feature the grouped members serve.
- Within each region, place **both member functions and member variables** of the same theme together.
- If a suitable region already exists, place new code inside it; do NOT create a duplicate region.
- If no matching region exists, create a new `#pragma region <ThemeName>` block for the new code.
- Do NOT create regions for includes or constructors/destructors; only use regions for thematic grouping.
  Example:
  ```cpp
  class PlayerCharacter
  {
  public:
      PlayerCharacter() = default;
      ~PlayerCharacter() = default;

  #pragma region Movement
  public:
      void Move(float dx, float dy);
      void Jump();
      float GetSpeed() const { return m_speed; }
  private:
      float m_speed = 5.0f;
      float m_jumpHeight = 2.0f;
  #pragma endregion Movement

  #pragma region Combat
  public:
      void Attack(Enemy& target);
      void TakeDamage(int amount);
      int GetHealth() const { return m_health; }
  private:
      int m_health = 100;
      int m_attackPower = 10;
  #pragma endregion Combat

  #pragma region Inventory
  public:
      void AddItem(const Item& item);
      void RemoveItem(int itemId);
      bool HasItem(int itemId) const;
  private:
      std::vector<Item> m_items = {};
  #pragma endregion Inventory
  };
  ```

## Security Requirements
- Do not hardcode sensitive information (passwords, keys, tokens, etc.) in code.
- Validate and sanitize user input appropriately.
- Follow the Principle of Least Privilege.

## Testing
- Write corresponding unit tests for new features.
- Test cases should cover normal flows and edge conditions.
- Maintain test code at the same quality as production code.

## Examples
// This is an English comment.
int Sum(int a, int b)
{
    return a + b; // English inline comment
}

// 说明: 上面的函数返回两个整数之和 (Chat explanation should be Chinese, not code comment)