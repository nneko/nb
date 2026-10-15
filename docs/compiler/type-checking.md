# Type checking

Implement static checking and inference.

## Behaviour

Types are checked at compile time, inferred where unambiguous, and incompatible assignments rejected.

## Specification in development

To be defined: Constraint solving, generic constraints, overloads, conversions, expression typing, ownership integration, and error reporting.

## Related specifications

[Language reference](../language/README.md) · [Compiler navigation](README.md) · [Platform](../platform/README.md)

[Specification status](../status.md)

## Calls and results

Check explicit -> results against final expressions or returns. Declarations without -> are void. Enforce bound-property types, lazy default restrictions, local/block shorthand lookup, duplicate bindings, variadic-name conflicts, ambiguity requiring labels, and read-only reflection metadata.
