# Internals

This chapters documents the internal design of the compiler and run-time. 

It is intended for Flix developers and *not* end-users.

- [Exceptions and Errors](exceptions-and-errors.md) - Discusses exceptions and error handling in the compiler and run-time.
- [Dependencies](dependencies.md) - Discusses the dependencies necessary to compile and build Flix.

### Compiler Phases

The compiler is split into several phases:

#### Frontend
- [Parsing](parsing.md)
- [Weeding](weeding.md)
- [Resolver](resolver.md)
- [Typer](typer.md)

#### Backend
- [Simplifier](simplifier.md)
- [Code Generator](code-generator.md)

#### Solver
- [Data Store](data-store.md)
- [Solver](solver.md)
