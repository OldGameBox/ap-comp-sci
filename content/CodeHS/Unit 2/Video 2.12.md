#java #loops #logic
- **Loop and a Half**: A specific programming pattern used to avoid repeating code when getting input. It involves starting an [[infinite loop]] and using a [[break statement]] to exit when a specific condition is met.
- **Why use it?**: In a standard [[while loop]], you often have to request input once before the loop and again inside the loop. The loop and a half structure consolidates this into one place.
- **The Process**:
    1. Use a `while(true)` loop.
    2. Request input from the user (using [[readLine()]], [[readInt()]], etc.).
    3. Immediately check if the input matches the [[sentinel]] value.
    4. If it matches, use a [[break statement]] to exit.
    5. Otherwise, process the data (e.g., add to an [[accumulator variable]]) and continue.