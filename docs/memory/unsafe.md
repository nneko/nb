# Unsafe operations

Explicit unsafe scopes authorize low-level operations that require additional programmer control.

## Syntax and examples

```nb
unsafe do
  let pointer = address(buffer)
end
```

## Semantics

Low-level memory operations require an explicit unsafe scope. address(buffer) obtains an address within that scope. Freestanding software supports explicit memory control.

## Rules and constraints

The guarantees suspended by unsafe operations, along with pointer layout, arithmetic, lifetime, and ABI rules, are specifications in development.

## To be defined

To be defined: Exact unsafe operation set, suspended guarantees, programmer obligations, pointer types, address lifetime, alignment, aliasing, and foreign-call requirements.

## Related specifications

[References](references.md) · [FFI](../interoperability/ffi.md) · [Freestanding](../platform/freestanding.md)

[Section navigation](README.md) · [Specification status](../status.md)
