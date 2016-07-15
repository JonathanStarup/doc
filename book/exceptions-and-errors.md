# Exceptions and Errors

Flix distinguishes between *compilation errors*, *program errors*, and *internal errors*.

### Compilation Errors

Compilation errors are errors caused by malformed Flix programs,
e.g. due to syntax errors, name errors, type errors, etc.
A malformed Flix program should never cause the Flix compiler nor run-time to unexpectedly fail.
Instead it is responsibility of the compiler to raise the appropriate compilation errors.

All *compilation errors* are organized in the hierarchy shown below:

- `CompilationError` - super-type of all compilation errors.
    - `SyntaxError` - super-type of all syntax errors.
        - `DuplicateAnnotation`
        - `DuplicateAttribute`
        - `DuplicateFormalArgument`
        - `DuplicateTag`
        - `NonLinearPattern`
        - ...
    - `ResolverError` - super-type of all resolver errors.
        - `DuplicateDefinition`
        - `IllegalVariableName`
        - `UnresolvedTagReference`
        - ...
    - `TypeError` - super-type of all type errors.
        - ...
    - `VerifierError` - super-type of all verifier errors.
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
        - `RuleException` - an exception thrown due to an integrity rule violation.
        - `SwitchException` - an exception thrown due to an incomplete switch.
        - `TimeoutException` - an exception thrown due to a user-specified timeout.

A *correct* Flix program should never throw any of these exceptions.

### Internal Errors

An error may occur in the Flix compiler or run-time. These errors are bugs (unexpected behaviour).

There are two types of exceptions that may be thrown:

- `java.lang.RuntimeException`
  - `InternalCompilerException` - an exception thrown by the compiler.
  - `InternalRuntimeException` - an exception thrown by the run-time.

If one of these exceptions is thrown then there is a bug in Flix.
