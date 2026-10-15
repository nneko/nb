# Interoperability boundary map

Native execution and foreign-language interoperability meet at the runtime, ABI, and linker. Their respective specifications cover the following interfaces.

| Concern | Owning document |
|---|---|
| Native nb binary conventions | [Native ABI](abi.md) |
| C-facing calls, layouts, and exports | [C ABI](../interoperability/c-abi.md) |
| Foreign declarations, memory, callbacks | [FFI](../interoperability/ffi.md) |
| .rb, #lang ruby, CRuby, gems | [Ruby compatibility](../interoperability/ruby.md) |
| Import/export adaptation and generation | [Bindings](../interoperability/bindings.md) |
| Object/library linking | [Linking](linking.md) |

To be defined: per-target support and runtime/linker requirements after the ABI, runtime, and foreign-boundary contracts are finalized. 

[Platform navigation](README.md)
