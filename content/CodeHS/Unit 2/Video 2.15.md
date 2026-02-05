#java #strings
- A **String** is a sequence of characters (e.g., "Hello World") enclosed in double quotes.
- Strings are **Objects**, not [[primitive types]]. This is why `String` starts with a capital **S**.
- **Operations**:
    - [[concatenation]]: Combining strings or a string and another variable type using the `+` operator.
- **Comparing Strings**:
    - **Never** use the `==` ([[equality operator]]) to compare strings; it is buggy and unreliable for object types.
    - Instead, use the [[String.equals()]] method to check if two strings contain the same characters.