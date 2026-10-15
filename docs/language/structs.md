# Structs

Structs provide value semantics, stored fields, and computed properties.

```nb
public struct Point

  public let x: float = 0.0
  public let y: float = 0.0

  public computed distance: float do
    (x * x + y * y).sqrt()
  end

end

let origin = Point.new()
let offset = Point.new(x: 10.0)
```

## Initial state

Without an explicit initial, public stored properties form an automatic public memberwise initialiser. Property defaults supply omitted arguments. Private and protected stored properties require defaults for that form; otherwise an explicit initial is required. Computed properties are not memberwise inputs.

Explicit initial declarations use state ... end, default to public, support property-bound parameters, and replace automatic initialisation. Every stored property must have an initial value before construction completes.

## Value semantics

Value semantics do not prescribe stack allocation or bitwise copying. Borrowing a derived struct through a base type preserves the complete value. Explicit conversion may produce a sliced base value. Single concrete inheritance is a specification in development.

Members default to private except initial declarations. Public APIs cannot expose inaccessible types.

## Specification in development

Struct inheritance, explicit sliced conversions, layout, dispatch, copying owned fields, and complete definite-initialisation analysis.

[Initial state](initial-state.md) · [Properties](properties.md) · [Borrowing](../memory/borrowing.md) · [Language reference](README.md)
