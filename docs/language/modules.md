# Modules and visibility

Every source file belongs to an implicit or explicit module. Imports and controlled module extensions organize package code.

## Syntax and examples

```nb
module Mathematics
  private let precision = 0.0001
  public def square(x: float) -> float do
    x * x
  end
end

import Mathematics from "./mathematics.nbs" as Math
let result = Math.square(5.0)

extend module Mathematics
  public def cube(x: float) -> float do
    x * x * x
  end
end
```

## Semantics

| Declaration | Default visibility |
|---|---|
| Module itself | public |
| Module-level declarations | private |
| Class/struct members other than initial | private |
| Initial-state declarations | public |
| Protocol requirements | public |

public makes declarations available through the public interface. protected permits authorized related declarations. private restricts access to the declaration's ownership boundary.

For modules specifically, private members are restricted to their original declaration block; protected members may be accessed by authorized extensions within the same package. Module extensions are allowed within a package. The task-manager uses Models::Task for qualified types.

## Rules and constraints

Extensions cannot modify arbitrary dependency modules. Public APIs cannot expose inaccessible types.

## To be defined

To be defined: Implicit module names, import search/resolution, initialization order, circular imports, export/re-export syntax, precise extension authorization, protected inheritance rules, and qualified-name grammar.

## Related specifications

[Packages](packages.md) · [Properties](properties.md) · [Bindings](../interoperability/bindings.md)

[Section navigation](README.md) · [Specification status](../status.md)

## Global functions

nb has a global namespace for unqualified functions. Source files still belong to modules. See [global namespace](namespaces.md).
