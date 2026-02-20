#java
- **[[String]]** objects are sequences of characters indexed starting at 0.
- Strings are [[immutable]], meaning they cannot be changed once created; methods that seem to modify a string actually return a new string.
- Common **[[String methods]]**:
    - [[length()]] - returns the number of characters.
    - [[charAt(int index)]] - returns the **[[char]]** at the specified index.
    - [[substring(int start, int end)]] - returns a part of the string from the start index (inclusive) to the end index (exclusive).
    - [[indexOf(String str)]] - returns the index of the first occurrence of a substring.
    - [[equals(String other)]] - compares characters of two strings for equality.
- You can loop over a string using a **[[for loop]]** combined with [[length()]] and [[charAt(int index)]].