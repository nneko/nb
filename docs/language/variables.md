# Variables

Bindings express whether a name can be reassigned. Type inference keeps declarations concise; annotations make intended types explicit.

## Syntax and examples

```nb
let name = "Alice"
var counter = 0
counter += 1

let fixed = 10
fixed = 11  # invalid: immutable binding
```

## Semantics

let creates an immutable binding. var creates a mutable binding. Binding mutability and mutability of a referenced object are separate concepts: an immutable name does not by itself establish deep immutability. self identifies the instance in initializer and member examples.

## Rules and constraints

Assignments must respect both binding mutability and type compatibility. A public API cannot expose an inaccessible type. Immutable fields are initialised during construction. A bound immutable property cannot be assigned again after its binding.

## To be defined

To be defined: Shadowing, definite initialization analysis, local scope boundaries, capture rules, complete definite-initialisation rules.

## Related specifications

[Types](types.md) · [Classes](classes.md) · [Ownership](../memory/ownership.md)

[Section navigation](README.md) · [Specification status](../status.md)
