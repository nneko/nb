# Generics

Generic functions and types express reusable abstractions with compile-time type parameters.

## Syntax and examples

```nb
def identity<T>(value: T) -> T do
  value
end

public struct Pair<T, U>
  public let first: T
  public let second: U
end

let pair = Pair<integer, string>.new(
  first: 10,
  second: "hello"
)
```

## Semantics

Angle brackets declare or apply type parameters. Type parameters appear in collections, optional types, and associated-value enums. array<float, 3> combines an element type with a fixed size. General compile-time value parameters are to be defined.

## Rules and constraints

Instantiations must respect type compatibility. Generic code generation is a specification in development. Structs follow [automatic initialisation](initial-state.md).

## To be defined

To be defined: Generic constraint syntax, inference boundaries, variance, specialization, recursion limits, generic protocol integration, and complete construction behavior.

## Related specifications

[Types](types.md) · [Protocols](protocols.md) · [Collections](collections.md)

[Section navigation](README.md) · [Specification status](../status.md)
