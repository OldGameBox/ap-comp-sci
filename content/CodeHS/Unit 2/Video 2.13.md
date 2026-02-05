#java #logic
- [[Short-circuit evaluation]] occurs when Java skips the evaluation of the second operand in a [[boolean]] expression because the first operand already determines the final result.
- **How it works with [[logical operators]]**:
    - [[logical AND]] (`&&`): If the first operand is `false`, the entire expression must be `false`. Java does **not** evaluate the second part.
    - [[logical OR]] (`||`): If the first operand is `true`, the entire expression must be `true`. Java does **not** evaluate the second part.
- **Practical Benefit**: Prevents program crashes, such as a "divide by zero" error.
    - _Example_: `if (numPeople != 0 && (slices / numPeople) > 0)`
    - If `numPeople` is `0`, the first part is `false`, and Java stops, skipping the division that would have caused a crash.
- You can verify this behavior by printing results using [[System.out.println()]].