# Allocation

Define allocation strategies and memory-management mechanisms.

## Behaviour

Ordinary application class references have managed lifetime semantics. Structs have value semantics. Freestanding programs must not require a mandatory garbage collector or general-purpose managed runtime.

## Specification in development

To be defined: Allocation locations, allocator interfaces, allocation failure, reference-counting implementation if selected, cycle handling, destruction, and hosted/freestanding profiles.

## Related specifications

[Classes](../language/classes.md) · [Freestanding](../platform/freestanding.md)

[Specification status](../status.md)
