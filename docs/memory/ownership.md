# Ownership

The ownership model distinguishes owning values, borrowing values, mutable borrowing, and transferring ownership.

## Syntax and examples

```nb
def consume(value: take Buffer) do
  process(value)
end
```

## Semantics

take marks ownership transfer to a parameter. Value ownership and managed class references have distinct lifetime behaviour. [Borrowing](borrowing.md) provides access without ownership transfer; [references](references.md) describe access to existing values.

## Rules and constraints

Move checking, copy eligibility, destruction order, and post-transfer diagnostics are specifications in development. Buffer and process stand for application-defined types and functions.

## To be defined

To be defined: Precise transfer semantics, use-after-transfer rules, implicit/explicit copies, ownership of composite fields, cleanup, and exceptions during transfer.

## Related specifications

[Borrowing](borrowing.md) · [Allocation](allocation.md) · [Lifetimes](lifetimes.md)

[Section navigation](README.md) · [Specification status](../status.md)
