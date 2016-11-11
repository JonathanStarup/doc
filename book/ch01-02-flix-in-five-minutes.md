# Flix in Five Minutes

| Classification                       | Description                                   |
|--------------------------------------|-----------------------------------------------|
| Paradigm                             | multi-paradigm: functional, logic             |
| Typing discipline                    | static, strong, safe, nominative              |
| Type inference                       | local Hindley-Milner                          |
| Type annotations                     | locally inferred, mandatory at top-level      |
| Evaluation mode                      | compilation to bytecode + interpretation      |
| Evaluation order                     | strict, call-by-value                         |
| Functions                            | pure (side-effect free), total                |
| Scope                                | lexical scope                                 |
| Fixedpoint Solver                    | bottom-up, parallel                           |
| Syntax inspired by                   | Scala, Python, OCaml, Datalog                 |
| Library inspired by                  | Scala, Haskell                                |
| Platform                             | Java / JVM 1.8+                               |
| Implementation language              | Scala                                         |
| License                              | Apache 2.0                                    |

#### Unsupported Features

By design Flix does not, and probably never will, support the following features:

***Null.***
Programming languages, such as Java and C#, allows the special value `null` to be assigned to any type. 
This unfortunate design choice leads to code littered with `if (x == null)` checks or runs the risk causing
`NullPointerException`s. Flix avoids this issue by requiring possible absent values to be represented by
the `Option` data type.

***Sub-Typing.***
Flix has powerful Hindley-Milner type inference, but not sub-typing.

***Implicit Coercions.***
Flix *does not* automatically convert values between types. For example, integers are not silently converted to booleans 
or strings.
