# Operators

nb provides arithmetic, comparison, boolean, assignment, optional-access, and range operators.

## Syntax and examples

```nb
counter += 1
value * value
x * x + y * y
value % 2 == 0
a / b
age >= 18
not enabled
enabled and ready
enabled && ready
name ?? "Guest"
name?.length
values[1..3]
```

## Semantics

The boolean operators and, or, not have equivalent symbolic forms &&, ||, !. Boolean operations require boolean-compatible operands; general truthiness is not assumed. Numeric overflow is checked by default. Integer division has integer semantics.

Operators include +, *, /, %, ==, <, >=, =, +=, safe access ?., coalescing ??, and the range form .. . Identity uses same rather than being inferred from equality. Parentheses can express grouping explicitly.

## Rules and constraints

The ! suffix of reset! is part of a method name, while prefix ! is a boolean operator. Optional ? suffix and predicate ? suffix occur in different grammatical positions. Range endpoint inclusion and operator precedence are to be defined.

## To be defined

To be defined: Complete operator inventory, precedence and associativity table, short-circuit/evaluation-order rules, overload rules, mixed numeric operations, range endpoints, and failure behavior.

## Related specifications

[Types](types.md) · [Control flow](control-flow.md) · [Collections](collections.md)

[Section navigation](README.md) · [Specification status](../status.md)
