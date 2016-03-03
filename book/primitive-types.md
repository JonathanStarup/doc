# Primitive Types

Flix has the primitive types: `Unit`, `Bool`, `Char`, `Int8`, `Int16`, `Int32`, `Int64` and `Str`:

| Flix Type | JVM Type  | Examples              | Description                               |
| --------- | --------- | --------------------- | ----------------------------------------- |
| Unit      | n/ a      | `()`                  | The Unit value.                           |
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
but has limited use in practice. That said, you can write a function that returns the `Unit`` value:

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
Implication and bicondition can be written in ASCII as `==>` and `<==>` , respectively.

### Char

### Int8

### Int16

### Int32

### Int64

