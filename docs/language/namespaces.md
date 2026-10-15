# Global namespace

nb has a global namespace. Standard functions can be called without a module or object qualifier; ordinary programming does not require object-oriented organisation.

```nb
print("Hello, world!")
print_warn("Task not found")
print_debug(task)
```

Modules continue to organise declarations, imports, visibility, and package boundaries. Every source file belongs to an implicit or explicit module. Global function availability does not remove that organisation.

Named-argument shorthand resolves only in local or block scope, without a global fallback.

## Specification in development

User-defined global declarations, global variables and mutability, exports, imports, shadowing, name conflicts, and initialisation order. Standard global functions do not by themselves define unrestricted mutable global state.

[Modules](modules.md) · [Arguments](arguments.md) · [Printing](../standard-library/printing.md) · [Language reference](README.md)
