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
- **size: Int**
    - Returns the number of bits used to represent the Int type.

### Int Operations
- **abs(i: Int): Int**
    - Returns the absolute value of i.
- **min(i1: Int, i2: Int): Int**
    - Returns the smallest of i1 and i2.
- **max(i1: Int, i2: Int): Int**
    - Returns the largest of i1 and i2.
- **dist(i1: Int, i2: Int): Int**
    - Returns the non-negative distance between i1 and i2.
    - Returns -1 if this distance is greater than maxValue.
- **compare(i1: Int, i2: Int): Int**
    - Returns 0 if i1-i2 is zero, -1 if i1-i2 is negative or 1 if i1-i2 is positive.
- **signum(i: Int): Int**
    - Returns 0 if i is zero, -1 if i is negative or 1 if i is positive.
- **logicalRightShift(i: Int, d: Int): Int**
    - Returns i right-shifted by d bits.
    - Zero extension is used (sign bit is not extended).
- **bitCount(i: Int): Int**
    - Returns the number of one-bits in the binary representation of i.
- **rotateRight(i: Int, d: Int): Int**
    - Returns the binary representation of i rotated right by d bits.
- **rotateLeft(i: Int, d: Int): Int**
    - Returns the binary representation of i rotated left by d bits.
- **highestOneBitPosition(i: Int): Int**
    - Returns the position of the highest-order/leftmost one-bit in i.
    - Possible return values: 0 (rightmost bit) to 31 (leftmost bit) or -1 if i=0.
- **lowestOneBitPosition(i: Int): Int**
    - Returns the position of the lowest-order/rightmost one-bit in i.
    - Possible return values: 0 (rightmost bit) to 31 (leftmost bit) or -1 if i=0.
- **highestOneBit(i: Int): Int**
    - Returns an int with at most a single one-bit, in the position of the highest-order/leftmost one-bit in i.
    - Returns 0 if i=0.
- **lowestOneBit(i: Int): Int**
    - Returns an int with at most a single one-bit, in the position of the lowest-order/rightmost one-bit in i.
    - Returns 0 if i=0.
- **numberOfLeadingZeros(i: Int): Int**
    - Returns the number of zero bits preceding the highest-order/leftmost one-bit in i.
    - Returns 32 if i=0.
- **numberOfTrailingZeros(i: Int): Int**
    - Returns the number of zero bits following the lowest-order/rightmost one-bit in i.
    - Returns 32 if i=0.
- **bit(i: Int, p: Int): Int**
    - Returns the bit of i at position p (either 0 or 1).
    - The bits of i have positions: 0 (rightmost bit) to 31 (leftmost bit)

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

