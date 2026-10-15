# Enums

Enums define a constrained set of cases, including cases carrying associated values.

## Syntax and examples

```nb
public enum Status
  case pending
  case active
  case completed
end

public enum Result<T, E>
  case success(T)
  case failure(E)
end
```

## Semantics

Enums may provide computed properties and pure boolean validation behavior. A computed property can match self to derive a value from the current case. Cases can carry associated values. A case name such as .pending can omit its enum type when the context identifies it.

## Rules and constraints

Enums are not unrestricted class-like objects with arbitrary methods. Enum-specific member visibility defaults remain to be formalized.

## To be defined

To be defined: Exact allowed validation grammar and purity rules, enum visibility defaults, associated-value construction/destructuring, case inference, exhaustiveness, representation, and equality.

## Related specifications

[Control flow](control-flow.md) · [Properties](properties.md) · [Task manager](../examples/task-manager.md)

[Section navigation](README.md) · [Specification status](../status.md)
