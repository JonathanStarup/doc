# Primitive Types

Flix has the primitive types: `Unit`, `Bool`, `Char`, `Int8`, `Int16`, `Int32`, `Int64` and `Str`:

| Flix Type | JVM Type  | Examples              | Description                               |
| --------- | --------- | --------------------- | ----------------------------------------- |
| Unit      | n/ a      | `()`                  | The unit value.                           |
| Bool      | boolean   | `true`, `false`       | A boolean, true or false.                 |
| Char      | char      | `'a'`, `'b'`, `'c'`   | A unicode character.                      |
| Int8      | byte      | `21i8`, `-42i8`       | A  8-bit signed integer.                  |
| Int16     | short     | `21i16`, `-42i16`     | A 16-bit signed integer.                  |
| Int32     | int       | `42`, `42i32`         | A 32-bit signed integer.                  |
| Int64     | long      | `21i64`, `-42i64`     | A 64-bit signed integer.                  |
| Str       | String    | `"foo"`, `"bar"`      | A string.                                 |

Note: The `Int32` type is available under the alias `Int`.

Note: The `Str` type may be removed in the future.

### Unit

The `Unit` type has the single value `()`. The `Unit` type exists to simplify the language design,
but has limited use in practice. That said, you can write a function that returns the `Unit` value:

```flix
def f: Unit = ()
```

### Bool

The `Bool` type has the two familiar boolean values: `true` and `false`:

```flix
def t: Bool = true
def f: Bool = false
```

Booleans support the usual operations:

```flix
def f(x: Bool): Bool = !x
def g(x: Bool, y: Bool): Bool = x && y
def h(x: Bool, y: Bool): Bool = x || y
def j(x: Bool, y: Bool): Bool = (x ∧ y) → (x ∨ y)
```

The last function shows that booleans also support the UTF-8 operators:
`¬` (not), `∧` (and), `∨` (or), `→` (implication), and `↔` (bicondition).
Implication and bicondition can be written in ASCII as `==>` and `<==>`, respectively.

### Char

The `Char` type represents unicode character values:

```flix
def a: Char = 'a'
def b: Char = 'b'
```

### Int8

The `Int8` type represents signed 8-bit integers. 

The minimum and maximum value an `Int8` can hold is `-2^7 = -128` and `2^7-1 = 127`, respectively.

```flix
def one: Int8 = 42i8 - 41i8
def min: Int8 = -128i8
def max: Int8 =  127i8
```

### Int16

The `Int16` type represents signed 16-bit integers.

The minimum and maximum value an `Int16` can hold is `-2^15 = -32768` and `2^15-1 = 32767`, respectively.

```flix
def one: Int16 = 42i16 - 41i16
def min: Int16 = -32768i16
def max: Int16 =  32767i16
```

### Int32

The `Int32` type represents signed 32-bit integers.

The minimum and maximum value an `Int32` can hold is `-2^31 = -2147483648` and `2^31-1 = 2147483647`, respectively.

```flix
def one: Int32 = 42i32 - 41i32
def min: Int32 = -2147483648i32
def max: Int32 =  2147483647i32
def two: Int = 2
```

Note that `Int` is an alias for `Int32` and that these values can be written without the `i32` suffix.

### Int64

The `Int64` type represents signed 64-bit integers.

The minimum and maximum value an `Int64` can hold is `-2^63 = -9223372036854775807` and `2^63-1 = 9223372036854775806`, respectively.


```flix
def one: Int64 = 42i64 - 41i64
def min: Int64 = -9223372036854775807i64
def max: Int64 =  9223372036854775806i64
```

### Operations on Int8, Int16, Int32 and Int32

The types `Int8`, `Int16`, `Int32` and `Int64` all support the operators:

| Operators                                         | Description                                                       |
| ------------------------------------------------- | ----------------------------------------------------------------- |
| `+`, `-`, `*`, `/`, `%`                           | addition, subtraction, multiplication, division, modulo.          |
| `<`, `<=`, `>`, `>=`                              | less than, less than equal, greater than, greater than equal.     |
| `&`, <code>&#124;</code> , `^`, `<<`, `>>`        | bitwise and, bitwise or, bitwise xor, left shift, right shift.    |

