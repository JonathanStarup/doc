# Exceptions

- java.lang.RuntimeException
  - InternalCompilerException (this is always cause for a bug report)
  - InternalRuntimeException  (this is always cause for a bug report)
  - FlixException
    - NotImplemented (this is always a user/programmer error.)
    - MatchException (this is always a user/programmer error.)
    - SwitchException (this is always a user/programmer error.)

and a separate hierarchy for compilation errors:

- CompilationError
  - SyntaxError
    - DuplicateFormalArgument
  - TypeError
    - ...
  - VerifierError
    - NonMonotone
    - ...
