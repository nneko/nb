# References

Explicit reference construction complements reference-oriented classes and borrowing.

## Syntax and examples

```nb
let reference = ref(buffer)
let mutable_reference = ref(mut buffer)
```

## Semantics

ref(buffer) constructs an explicit reference; ref(mut buffer) expresses a mutable reference. Safe references and raw pointers are distinct concerns. Class identity uses same as documented under classes.

## Rules and constraints

Reference construction does not settle a surface reference type grammar, dereferencing syntax, implicit conversions, or lifetime rules. The immutable name of a reference and access permissions through the reference are separate.

## To be defined

To be defined: Reference types and dereferencing, validity, alias permissions, nullable references, conversions, and representation.

## Related specifications

[Borrowing](borrowing.md) · [Lifetimes](lifetimes.md) · [Unsafe](unsafe.md)

[Section navigation](README.md) · [Specification status](../status.md)
