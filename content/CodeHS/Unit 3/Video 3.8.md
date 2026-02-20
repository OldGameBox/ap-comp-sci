#java
- **String Processing** involves combining string and character manipulation to perform advanced tasks.
- A common idiom for processing strings:
    1. Create a "result" string (often initialized as an empty string `""`).
    2. Loop through every character in the original string.
    3. Perform an action with each character (e.g., adding it to the result).
    4. Return the result.
- **[[Pseudocode]]** - an English description of a program's steps that helps plan the logic before writing actual code.
- Example: Checking for a **[[Palindrome]]**:
    - Reversing a string: Use a **[[for loop]]** starting from `text.length() - 1` down to `0` and **[[concatenation|concatenate]]** each character to a result string.
    - Comparison: Use **[[String.equals()]]** to see if the original matches the reversed version.