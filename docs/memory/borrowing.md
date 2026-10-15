# Borrowing

Borrowing permits access to a value without expressing ownership transfer.

## Syntax and examples

```nb
def inspect(value: borrow Buffer) do
  print(value.length)
end

def modify(value: borrow mut Buffer) do
  value.clear()
end
```

## Semantics

borrow requests immutable access; borrow mut requests mutable access. A base-type borrow preserves the complete derived value. Exclusivity, aliasing, reborrowing, and escape rules are specifications in development.

borrow is immutable borrowing; borrow mut is mutable borrowing. When a derived struct is borrowed through a base type, the complete value is preserved.

## Rules and constraints

The concurrency model aims to prevent unsynchronised mutable access.

## To be defined

To be defined: Exclusivity, alias overlap, reborrowing, temporary borrows, escape analysis, capture restrictions, and interactions with mutation, concurrency, and errors.

## Related specifications

[Ownership](ownership.md) · [References](references.md) · [Structs](../language/structs.md)

[Section navigation](README.md) · [Specification status](../status.md)
