# Namespaces

Namespaces allow the same name to be used in different contexts. 
Namespaces are *not* objects, classes, or modules. 
They are simply a fancy way of sticking one name in front of another.

As a concrete example, we can define two *different* functions both named `f` in different namespaces:

```flix
namespace a {
    def f: Bool = true
}

namespace b {
    def f: Char = 'a'
}
```

Inside the namespace `a` the function `f` is visible with type `Bool`, 
whereas inside the namespace `b` the function `f` is visible with type `Char`.

We can explicitly refer to a function (or other declaration) in a namespace 
by prefixing it with its fully qualified name. In this case, we have the two 
functions `a/f` and `b/f`.

A namespace can use multiple identifiers, for example:

```flix
namespace a.b.c {
    def f: Bool = true
}
```

this is equivalent to:

```flix
namespace a {
    namespace b {
        namespace c {
            def f: Bool = true
        }
    }
}
```

In both cases we can explicitly refer to the function `f` as `a.b.c/f`.

It is common, but not required, that a namespace such as `a.b.c`. reside in a file called `a/b/c.flix`.

The members of a namespace does not have to be declared in a single declaration.
For example, the following is perfectly legal:

```flix
namespace a {
    def f: Int = 21
    def g: Int = 42
}

namespace a {
    def h: Bool = f + g
}
```

Although possible, adding members to a Flix standard library namespace is not recommended.

## Importing Namespaces

Namespaces can be imported in three different ways:

```flix
import a.b.c/_
import a.b.c/fooBar
import a.b.c
```

The first imports every definition inside the `a.b.c` namespace.
The second imports the definition named `fooBar` in the `a.b.c` namespace.
The third imports the `a.b.c` namespace.

## Type Classes

Namespace and type classes do not interact: Type class names (and instances) are always globally visible, 
regardless of what namespace they are declared in. 
