# Architecture

Compiler pipeline and component boundaries.

## Behaviour

The compilation pipeline is lexical analysis → parser/AST → semantic analysis → type checking → ownership and borrow checking → IR → optimization → native code generation → executable/library. Outputs include native executables, shared libraries, static libraries, and constrained freestanding programs.

## Specification in development

To be defined: Component APIs, pass organization, incremental compilation, host/target separation, backend and IR selection. The pipeline order is an architectural description, not a mandated pass implementation.

## Related specifications

[Language reference](../language/README.md) · [Compiler navigation](README.md) · [Platform](../platform/README.md)

[Specification status](../status.md)
