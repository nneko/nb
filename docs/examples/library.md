# Library

```nb
module Mathematics
  public def square(x: float) -> float do
    x * x
  end
end
```

Consumer in another source file:

```nb
import Mathematics from "./mathematics.nbs" as Math
let result = Math.square(5.0)
```

Store production code in source/. Introduce interfaces/ only when public interface artifacts are defined and needed. A public function must not expose inaccessible types.

To be defined: Library manifest, static/shared artifact configuration, exported interface format, and ABI stability.

[Modules](../language/modules.md) · [Linking](../platform/linking.md) · [Example navigation](README.md)
