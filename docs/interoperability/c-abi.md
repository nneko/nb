# C ABI

Define how values and calls cross the C boundary.

## Behaviour

C ABI compatibility is the primary foreign-function boundary for native libraries and system interfaces. C-facing type representations, calling conventions, exported symbols, and linking contracts define that boundary. Native nb ABI rules remain in platform/abi.md.

## Specification in development

To be defined: Per-target C type mapping, layouts, calling conventions, exports, variadic calls, strings, ownership, callbacks, error boundaries, and compatibility versions. Foreign declaration syntax is to be defined.

## Related specifications

[Native ABI](../platform/abi.md) · [Linking](../platform/linking.md) · [FFI](ffi.md)

[Specification status](../status.md)
