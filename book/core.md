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

## Int8
### Int8 Constants
- **minValue: Int8**
    - Returns the minimum value representable by the Int8 type.
- **maxValue: Int8**
    - Returns the maximum value representable by the Int8 type.
- **size: Int**
    - Returns the number of bits used to represent the Int8 type.

### Int8 Operations
- **abs(i: Int8): Int8**
    - Returns the absolute value of i.
    - Returns -1 if i is minValue.
- **min(i1: Int8, i2: Int8): Int8**
    - Returns the smallest of i1 and i2.
- **max(i1: Int8, i2: Int8): Int8**
    - Returns the largest of i1 and i2.
- **dist(i1: Int8, i2: Int8): Int8**
    - Returns the non-negative distance between i1 and i2.
    - Returns -1 if this distance is greater than maxValue.
- **compare(i1: Int8, i2: Int8): Int**
    - Returns 0 if i1-i2 is zero, -1 if i1-i2 is negative or 1 if i1-i2 is positive.
- **signum(i: Int8): Int**
    - Returns 0 if i is zero, -1 if i is negative or 1 if i is positive.
- **highestOneBitPosition(i: Int8): Int**
    - Returns the position of the highest-order/leftmost one-bit in i.
    - Possible return values: 0 (rightmost bit) to 7 (leftmost bit) or -1 if i=0.
- **lowestOneBitPosition(i: Int8): Int**
    - Returns the position of the lowest-order/rightmost one-bit in i.
    - Possible return values: 0 (rightmost bit) to 7 (leftmost bit) or -1 if i=0.
- **highestOneBit(i: Int8): Int8**
    - Returns an Int8 with at most a single one-bit, in the position of the highest-order/leftmost one-bit in i.
    - Returns 0 if i=0.
- **lowestOneBit(i: Int8): Int8**
    - Returns an Int8 with at most a single one-bit, in the position of the lowest-order/rightmost one-bit in i.
    - Returns 0 if i=0.
- **numberOfLeadingZeros(i: Int8): Int**
    - Returns the number of zero bits preceding the highest-order/leftmost one-bit in i.
    - Returns 8 if i=0.
- **numberOfTrailingZeros(i: Int8): Int**
    - Returns the number of zero bits following the lowest-order/rightmost one-bit in i.
    - Returns 8 if i=0.
- **bit(i: Int8, p: Int): Int**
    - Returns the bit of i at position p (either 0 or 1).
    - The bits of i have positions: 0 (rightmost bit) to 7 (leftmost bit)

## Int16
### Int16 Constants
- **minValue: Int16**
    - Returns the minimum value representable by the Int16 type.
- **maxValue: Int16**
    - Returns the maximum value representable by the Int16 type.
- **size: Int**
    - Returns the number of bits used to represent the Int16 type.

### Int16 Operations
- **abs(i: Int16): Int16**
    - Returns the absolute value of i.
    - Returns -1 if i is minValue.
- **min(i1: Int16, i2: Int16): Int16**
    - Returns the smallest of i1 and i2.
- **max(i1: Int16, i2: Int16): Int16**
    - Returns the largest of i1 and i2.
- **dist(i1: Int16, i2: Int16): Int16**
    - Returns the non-negative distance between i1 and i2.
    - Returns -1 if this distance is greater than maxValue.
- **compare(i1: Int16, i2: Int16): Int**
    - Returns 0 if i1-i2 is zero, -1 if i1-i2 is negative or 1 if i1-i2 is positive.
- **signum(i: Int16): Int**
    - Returns 0 if i is zero, -1 if i is negative or 1 if i is positive.
- **highestOneBitPosition(i: Int16): Int**
    - Returns the position of the highest-order/leftmost one-bit in i.
    - Possible return values: 0 (rightmost bit) to 15 (leftmost bit) or -1 if i=0.
- **lowestOneBitPosition(i: Int16): Int**
    - Returns the position of the lowest-order/rightmost one-bit in i.
    - Possible return values: 0 (rightmost bit) to 15 (leftmost bit) or -1 if i=0.
- **highestOneBit(i: Int16): Int16**
    - Returns an Int16 with at most a single one-bit, in the position of the highest-order/leftmost one-bit in i.
    - Returns 0 if i=0.
- **lowestOneBit(i: Int16): Int16**
    - Returns an Int16 with at most a single one-bit, in the position of the lowest-order/rightmost one-bit in i.
    - Returns 0 if i=0.
- **numberOfLeadingZeros(i: Int16): Int**
    - Returns the number of zero bits preceding the highest-order/leftmost one-bit in i.
    - Returns 16 if i=0.
- **numberOfTrailingZeros(i: Int16): Int**
    - Returns the number of zero bits following the lowest-order/rightmost one-bit in i.
    - Returns 16 if i=0.
- **bit(i: Int16, p: Int): Int**
    - Returns the bit of i at position p (either 0 or 1).
    - The bits of i have positions: 0 (rightmost bit) to 15 (leftmost bit)

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
    - Returns -1 if i is minValue.
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

## Int64
### Int64 Constants
- **minValue: Int64**
    - Returns the minimum value representable by the Int64 type.
- **maxValue: Int64**
    - Returns the maximum value representable by the Int64 type.
- **size: Int**
    - Returns the number of bits used to represent the Int64 type.

### Int64 Operations
- **abs(i: Int64): Int64**
    - Returns the absolute value of i.
    - Returns -1 if i is minValue.
- **min(i1: Int64, i2: Int64): Int64**
    - Returns the smallest of i1 and i2.
- **max(i1: Int64, i2: Int64): Int64**
    - Returns the largest of i1 and i2.
- **dist(i1: Int64, i2: Int64): Int64**
    - Returns the non-negative distance between i1 and i2.
    - Returns -1 if this distance is greater than maxValue.
- **compare(i1: Int64, i2: Int64): Int**
    - Returns 0 if i1-i2 is zero, -1 if i1-i2 is negative or 1 if i1-i2 is positive.
- **signum(i: Int64): Int**
    - Returns 0 if i is zero, -1 if i is negative or 1 if i is positive.
- **logicalRightShift(i: Int64, d: Int): Int64**
    - Returns i right-shifted by d bits.
    - Zero extension is used (sign bit is not extended).
- **bitCount(i: Int64): Int**
    - Returns the number of one-bits in the binary representation of i.
- **rotateRight(i: Int64, d: Int): Int64**
    - Returns the binary representation of i rotated right by d bits.
- **rotateLeft(i: Int64, d: Int): Int64**
    - Returns the binary representation of i rotated left by d bits.
- **highestOneBitPosition(i: Int64): Int**
    - Returns the position of the highest-order/leftmost one-bit in i.
    - Possible return values: 0 (rightmost bit) to 63 (leftmost bit) or -1 if i=0.
- **lowestOneBitPosition(i: Int64): Int**
    - Returns the position of the lowest-order/rightmost one-bit in i.
    - Possible return values: 0 (rightmost bit) to 63 (leftmost bit) or -1 if i=0.
- **highestOneBit(i: Int64): Int64**
    - Returns an Int64 with at most a single one-bit, in the position of the highest-order/leftmost one-bit in i.
    - Returns 0 if i=0.
- **lowestOneBit(i: Int64): Int64**
    - Returns an Int64 with at most a single one-bit, in the position of the lowest-order/rightmost one-bit in i.
    - Returns 0 if i=0.
- **numberOfLeadingZeros(i: Int64): Int**
    - Returns the number of zero bits preceding the highest-order/leftmost one-bit in i.
    - Returns 64 if i=0.
- **numberOfTrailingZeros(i: Int64): Int**
    - Returns the number of zero bits following the lowest-order/rightmost one-bit in i.
    - Returns 64 if i=0.
- **bit(i: Int64, p: Int): Int**
    - Returns the bit of i at position p (either 0 or 1).
    - The bits of i have positions: 0 (rightmost bit) to 63 (leftmost bit)

## BigInt
### BigInt Operations
- **abs(i: BigInt): BigInt**
    - Returns the absolute value of i.
- **min(i1: BigInt, i2: BigInt): BigInt**
    - Returns the smallest of i1 and i2.
- **max(i1: BigInt, i2: BigInt): BigInt**
    - Returns the largest of i1 and i2.
- **dist(i1: BigInt, i2: BigInt): BigInt**
    - Returns the non-negative distance between i1 and i2.
- **compare(i1: BigInt, i2: BigInt): Int**
    - Returns 0 if i1-i2 is zero, -1 if i1-i2 is negative or 1 if i1-i2 is positive.
- **signum(i: BigInt): Int**
    - Returns 0 if i is zero, -1 if i is negative or 1 if i is positive.
- **bit(i: BigInt, p: Int): Int**
    - Returns the bit of i at position p (either 0 or 1).
    - The bits of i start at position 0 (rightmost bit) and increase to the left.
- **gcd(i1: BigInt, i2: BigInt): BigInt**
    - Returns the greatest common positive divisor of i1 and i2.
- **setBit(i: BigInt, p: Int): BigInt**
    - Returns i with the bit at position p set to 1 (returns i | (1 << position)).
- **clearBit(i: BigInt, p: Int): BigInt**
    - Returns i with the bit at position p cleared to 0 (returns i & ~(1 << position)).
- **flipBit(i: BigInt, p: Int): BigInt**
    - Returns i with the bit at position p flipped (returns i ^ (1 << position)).

## Float32
### Float32 Constants
- **minValue: Float32**
    - Returns the minimum value representable by the Float32 type.
- **maxValue: Float32**
    - Returns the maximum value representable by the Float32 type.
- **size: Int**
    - Returns the number of bits used to represent the Float32 type.
- **minPositiveValue: Float32**
    - Returns the minimum positive value representable by the Float32 type.
- **maxExponent: Int**
    - Returns the maximum exponent that the Float32 type may have.
- **minExponent: Int**
    - Returns the minimum exponent that the Float32 type may have.
- **undefined: Float32**
    - Returns the NaN (not a number) value of type Float32.
- **positiveInfinity: Float32**
    - Returns the positive infinity value of type Float32.
- **negativeInfinity: Float32**
    - Returns the negative infinity value of type Float32.

### Float32 Operations
- **min(i1: Float32, i2: Float32): Float32**
    - Returns the smallest of i1 and i2.
- **max(i1: Float32, i2: Float32): Float32**
    - Returns the largest of i1 and i2.

## Float64
### Float64 Constants
- **minValue: Float64**
    - Returns the minimum value representable by the Float64 type.
- **maxValue: Float64**
    - Returns the maximum value representable by the Float64 type.
- **size: Int**
    - Returns the number of bits used to represent the Float64 type.
- **minPositiveValue: Float64**
    - Returns the minimum positive value representable by the Float64 type.
- **maxExponent: Int**
    - Returns the maximum exponent that the Float64 type may have.
- **minExponent: Int**
    - Returns the minimum exponent that the Float64 type may have.
- **undefined: Float64**
    - Returns the NaN (not a number) value of type Float64.
- **positiveInfinity: Float64**
    - Returns the positive infinity value of type Float64.
- **negativeInfinity: Float64**
    - Returns the negative infinity value of type Float64.

### Float64 Operations
- **min(i1: Float64, i2: Float64): Float64**
    - Returns the smallest of i1 and i2.
- **max(i1: Float64, i2: Float64): Float64**
    - Returns the largest of i1 and i2.

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

