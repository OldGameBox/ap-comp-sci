#java #logic #control-flow 
- [[De Morgan's Laws]] are rules that show how to negate [[logical AND]] (`&&`) and [[logical OR]] (`||`) expressions.
- These laws are used to simplify complex [[boolean]] expressions or make them more readable.
- **The Core Rules**:
    - `!(A && B)` is equivalent to `!A || !B`
    - `!(A || B)` is equivalent to `!A && !B`
- **Distribution Pattern**: To apply the law, you "distribute" the [[logical NOT]] (`!`) operator across the statement:
    1. Negate the first term.
    2. Flip the operator (`&&` becomes `||`, and `||` becomes `&&`).
    3. Negate the second term.
- **Verification**: These logical equivalencies can be proven using [[truth tables]] or Venn diagrams.