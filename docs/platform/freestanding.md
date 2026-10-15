# Freestanding execution

Execute without a hosted operating-system runtime.

## Behaviour

Freestanding nb must not require a mandatory garbage collector or general-purpose managed runtime. Deterministic resource management and explicit memory control are design goals.

## Specification in development

To be defined: Entry/exit contracts, runtime/library subset, allocation policy, panic/error paths, interrupts, synchronization, linking, and target profiles.

## Related specifications

[Platform navigation](README.md) · [Memory](../memory/README.md) · [C ABI](../interoperability/c-abi.md)

[Specification status](../status.md)
