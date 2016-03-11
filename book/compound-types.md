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

### Opt

The `Opt` (short for option) data type has one of two values: `None` or `Some(v)` where `v` is a nested value.
The `Opt` data type is typically used to indict that some value may be missing (corresponding to `None`):

```flix
def f: Opt[Int] = None
def g: Opt[Int] = Some(42)
```

For efficiency, the Flix compiler eliminates the `Opt` type and uses the `null` value on the JVM.
This means that the use of `Opt` has no overhead. A drawback is that Flix cannot support nested options
with this scheme.

We can retrieve the value of an `Opt` with pattern matching:

```flix
def f(o: Opt[Int]): Int = match o with {
  case None => 42
  case Some(v) => v
}
```

### List

The `List` data type represents an immutable linked list.
The empty listed is denoted by `Nil` and a cons cell is denoted by the special syntax `::`.
Here is how to construct some lists:

```flix
def f: List[Int] = Nil
def g: List[Int] = 1 :: Nil
def h: List[Int] = 1 :: 2 :: Nil
def i: List[Int] = 1 :: 2 :: 3 :: Nil
```

Lists can be destructed with pattern matching:

```flix
def f(xs: List[Int): Int = match xs with {
    case Nil => 0
    case x :: xs => x + f(xs)
}
```

Another example:

```flix
def f(xs: List[Int): Bool = match xs with {
    case Nil => true
    case x :: Nil => false
    case x :: y :: Nil => f(xs)
}
```

### Set

The `Set` data type represents an immutable unordered collection of values.
Sets are denoted by the special syntax `#{...}`.
Here is how to construct some sets:

```flix
def f: Set[Int] = #{}         // the empty set
def g: Set[Int] = #{1}        // a singleton set
def h: Set[Int] = #{1, 2, 3}  // another set
```

You can even destruct sets with pattern matching:

```flix
def f(s: Set[Int): Int = match s with {
    case #{} => 0
    case #{x} => 1
    case #{x, xs...} => 1 + f(xs)
}
```

The syntax `xs...` denotes the rest of the set.
Thus, the last pattern matches an element of the set `x` and the remainder of the set `xs...`.

> ***Warning***: Flix does not guarantee that sets are deconstructed in any specific order.
> You must ensure that any destructuring is associative (order agnostic).

As another example:

```flix
def f(s: Set[Int): Bool = match s with {
    case #{1, x, 3, y} => true
    case _             => false
}
```

Here `f` returns `true` if  given a set that contains exactly four elements of which two are `1` and `3`.

