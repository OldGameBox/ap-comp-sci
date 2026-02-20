#java
- Bugs are helpful for learning and fixing broken code.
- **[[Compile-time errors]]** occur when the Java code has syntax errors (e.g., missing semicolons, mismatched parentheses, or incorrect types). The code will not run at all.
- **[[Runtime errors]]** occur while the program is running, even if the syntax is correct. These cause the program to crash.
- When a runtime error occurs, an **[[Exception]]** is thrown, providing info about what went wrong.
- Common Exceptions:
    - **[[ArithmeticException]]**: Occurs during bad math operations, most commonly dividing by zero.
    - **[[IndexOutOfBoundsException]]**: Occurs when trying to access an index that doesn't exist (e.g., a negative index or an index beyond a string's length).
    - **[[IllegalArgumentException]]**: Occurs when a method receives an argument that is technically the right type but doesn't make logical sense.