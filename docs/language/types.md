# Types

nb is statically typed. The compiler infers types when unambiguous and rejects incompatible assignments.

## Syntax and examples

```nb
let name = "Alice"
let age: integer = 30
let enabled: boolean = true
let price: decimal = 19.95
let small: i8 = 12
let ratio: float = 0.75
let precision: f64 = 3.14159

let optional_name: string? = nil
let length = optional_name?.length
let display_name = optional_name ?? "Guest"
if let value = optional_name
  print(value)
end
let value = optional_name.unwrap()
```

## Semantics

| Type | Meaning |
|---|---|
| boolean | Boolean values |
| byte | Byte representation |
| integer | Signed integer |
| uint | Unsigned integer |
| number | Arbitrary-precision numeric value |
| float | Default floating-point number |
| decimal | Decimal arithmetic |
| string | Unicode text |
| i8–i128 | Fixed-width signed integer family |
| u8–u128 | Fixed-width unsigned integer family |
| f16–f64 | Floating-point family |
| usize | Platform-sized unsigned integer |

Built-in types participate in the object model, including calls such as value.to_string(). Numeric overflow is checked by default. Wrapping and saturating operations require explicit mechanisms; their syntax is to be defined. Integer division follows integer semantics.

T? represents an optional value; nil represents absence. ?. performs safe member access, ?? supplies a fallback, if let conditionally unwraps, and unwrap() explicitly unwraps.

## Rules and constraints

Assignments must respect both type compatibility and binding mutability. An invalid unwrap is not silently accepted.

An incompatible assignment is invalid. An invalid unwrap is not silently accepted.

```nb
var age: integer = 30
age = "thirty"  # invalid: incompatible type
```

## To be defined

To be defined: Default integer widths, exact numeric representations, literal inference, conversion rules, division rounding for negative operands, overflow failure behavior, wrapping/saturating API, optional chaining result typing, invalid-unwrap failure mechanism, and boolean-compatible type set.

## Related specifications

[Variables](variables.md) · [Operators](operators.md) · [Numbers](../standard-library/numbers.md) · [Strings](../standard-library/strings.md)

[Section navigation](README.md) · [Specification status](../status.md)
