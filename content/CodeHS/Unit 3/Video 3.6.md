#java
- **[[String]]** vs. **[[char]]**:
    - Strings use double quotes (`""`), are objects, and are compared with `.equals()`.
    - Chars use single quotes (`''`), are **[[primitive types]]**, and are compared with `==`.
- **[[char]]** values are actually numeric values behind the scenes, based on the **[[ASCII]]** table.
    - You can cast a `char` to an `int` to see its numeric value.
    - You can perform arithmetic on chars (e.g., `'C' - 'A'` equals 2).
- **[[Escape sequences]]** are special characters starting with a backslash (`\`) used to represent things like new lines or quotes within a string.
- The **[[Character class]]** (capital 'C') provides static methods to manipulate or check `char` values.
    - Examples: `Character.isDigit(ch)`, `Character.isLetter(ch)`, `Character.toUpperCase(ch)`.