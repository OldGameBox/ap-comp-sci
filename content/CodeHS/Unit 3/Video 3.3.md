#java
- Methods can give back results called **return values**, which allow the caller to keep and use the result of a calculation.
- **[[return types]]** - the type of value a method gives back (e.g., `int`, `double`, `boolean`), specified in the method header.
- **[[return statement]]** - uses the `return` keyword to exit a method and send a value back to the caller.
- **[[method signature]]** - the combination of the method name and its parameter list.
- If a method has a return type (other than `void`), you can:
    - Save the result in a variable: `int result = sum(5, 8);`
    - Use it directly in an expression or print statement: `System.out.println(sum(10, 20));`
- If you try to assign a `void` method to a variable, it will result in an error.