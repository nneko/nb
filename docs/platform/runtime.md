# Runtime

Execution support required by language capabilities.

## Behaviour

Class references have managed lifetime semantics in ordinary application environments. Freestanding execution must not require a mandatory collector or general-purpose managed runtime. Ruby-independent programs do not require CRuby.

## Specification in development

To be defined: Runtime profiles, initialization, allocation/lifetime implementation, error machinery, concurrency support, library subsets, and embedding.

## Related specifications

[Platform navigation](README.md) · [Memory](../memory/README.md) · [C ABI](../interoperability/c-abi.md)

[Specification status](../status.md)
