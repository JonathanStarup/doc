# Compound Types

### Tuples
 
Tuples are easy to construct using parentheses:

```flix
def point2d: (Int, Int) = (21, 42)
def point3d: (Int, Int, Int) = (21, 42, 84)
```

Here `(Int, Int)` is a the type of a tuple with two `Int` components.
`Int` is an alias for `Int32` so the type is really `(Int32, Int32)`. 

Tuples can contain values of different types:

```flix
def t: (Bool, Char, Int8) = (true, 'a', 42i8)
```

We can extract the values of a tuple using pattern matching:

```flix
def f(point: (Int, Int)): Int = match point with {
    case (x, y) => x + y
}
```

or using a pattern matching let-binding:

```flix
def f(point: (Int, Int)): Int =
    let (x, y) = point in
        x + y
```
