# Core

## Bool
### Bool Operations
- **&&(b1: Bool, b2: Bool): Bool**
    - Returns true if both b1 and b2 are true. 
- **||(b1: Bool, b2: Bool): Bool**
    - Returns true if at least one of b1 and b2 is true.

## Char
### Char Predicates
- **isAscii(c: Char): Bool**
    - Returns true iff the character is an ASCII character.
- **isLetter(c: Char): Bool**
    - Returns true iff the character is a letter.
- **isDigit(c: Char): Bool**
    - Returns true iff the character is in the range 0...9.
- **isOctDigit(c: Char): Bool**
    - Returns true iff the character is in the range 0...7.
- **isHexDigit(c: Char): Bool**
    - Returns true iff the character is in the range 0...F.
- **isLower(c: Char): Bool**
    - Returns true iff the character is a lowercase letter.
- **isUpper(c: Char): Bool**
    - Returns true iff the character is an uppercase letter.
- **isWhiteSpace(c: Char): Bool**
    - Returns true iff the character is a white space character.

### Char Conversions
- **toLower(c: Char): Char**
    - Converts a letter to its lowercase version. 
    - Returns the original character if it does not have a lowercase version.
- **toUpper(c: Char): Char**
    - Converts a letter to its uppercase version.
    - Returns the original character if it does not have an uppercase version.
- **toInt(c: Char): Int**
    - Converts the character to an integer.

## Int
### Int Constants
- **minValue: Int**
    - Returns the minimum value representable by the Int type.
- **maxValue: Int**
    - Returns the maximum value representable by the Int type.

### Int Operations
- **abs(i: Int): Int**
    - Returns the absolute value of i.
- **min(i1: Int, i2: Int): Int**
    - Returns the smallest of i1 and i2.
- **max(i1: Int, i2: Int): Int**
    - Returns the largest of i1 and i2.

### Int Conversions
- **toChar(i: Int): Char**
    - Converts an Int to a Char.

## Debugging
Operations for debugging Flix programs.

Note: The Flix language does not guarantee the semantics of these operations.

- **abort(m: String): Unit**
    - Immediately aborts execution and prints the message m.
- **print(a: A): A**
    - Prints the value a and returns it.
- **time(f: () => A): A**
    - Measures the execution time of the function f. 
    - Returns the result of evaluating the function.

