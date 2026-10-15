# Parser

Parse source into an AST.

## Behaviour

Ordinary functions use do ... end; initial-state declarations use state ... end. Brace closures place result annotations after the closing brace. Parameters support defaults and final variadic markers; spread is postfix ... . Formal grammar is not finalized.

## Specification in development

To be defined: Complete grammar, precedence, ambiguities, AST schema, source fidelity, and recovery.

## Related specifications

[Language reference](../language/README.md) · [Compiler navigation](README.md) · [Platform](../platform/README.md)

[Specification status](../status.md)
