# Exceptions and Errors

Flix distinguishes between *compilation errors*, *program errors*, and *internal errors*.

### Compilation Errors

The compiler and run-time should never fail unexpectedly because of an erroneous Flix program.
If a Flix program is malformed it is responsibility of the compiler to raise the appropriate
compilation errors. These errors are a completely normally occurrence in the Flix compiler.

Compilation errors are organized in a hierarchy with `CompilationError` at the root:

- `CompilationError` - super-type of any compilation error.
    - `SyntaxError` - super-type of any syntax error.
        - `DuplicateFormalArgument` - a specific syntax error.
        - `NonLinearPattern` - a specific syntax error.
        - ...
    - `ResolverError` - a super-type of any resolver error.
        - `DuplicateDefinition` - a specific resolver error.
        - `IllegalVariableName` - a specific resolver error.
        - ...
    - `TypeError` - super-type of any type error.
        - ...
    - `VerifierError` - super-type of any verifier error.
        - ...

Note that `CompilationError` is ***not*** a (Java) exception nor is it a (Java) error. It is simply an interface.
`CompilationErrors` are never thrown, but are instead collected by the phases of the compiler.

### Program Errors

Flix programs may themselves be erroneous.
This gives rise to `FlixException`s that may be thrown at run-time as shown below:

- `java.lang.RuntimeException`
    - `FlixException` - a common super-type for exceptions caused by Flix programs.
        - `UserException` - an exception explicitly thrown by the programmer.
        - `MatchException` - an exception thrown due to an incomplete match.
        - `SwitchException` - an exception thrown due to an incomplete switch.

A *correct* Flix program should never throw any of these exceptions.

### Internal Errors

An error may occur in the Flix compiler or run-time. These errors are bugs (unexpected behaviour).

There are two types of exceptions that may be thrown:

- `java.lang.RuntimeException`
  - `InternalCompilerException` - an exception thrown by the compiler.
  - `InternalRuntimeException` - an exception thrown by the run-time.

If one of these exceptions is thrown then there is a bug in Flix.
