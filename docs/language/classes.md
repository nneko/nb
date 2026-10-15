# Classes

Classes provide reference semantics, encapsulated state, and single concrete inheritance.

## Initial state

```nb
public class User

  private let name_value: string

  def initial(@name_value) state
  end

  public computed name: string do
    name_value
  end

end

let user = User.new(name_value: "Alice")
```

initial is public by default and uses state ... end. A bound parameter takes its type and default from the property. Bindings occur before the state body. private or protected restricts initialiser access explicitly.

## Reference semantics

Ordinary application environments manage class-reference lifetimes. Object identity is distinct from value equality and can be queried with same. An immutable binding can refer to an object with mutable state.

Classes support one concrete base and may conform to protocols. Members default to private, except initial declarations, which default to public. Public APIs cannot expose inaccessible types.

## Specification in development

Initialiser inheritance/delegation, overriding, dispatch, destruction, equality, detailed protected access, and managed lifetime implementation.

[Initial state](initial-state.md) · [Protocols](protocols.md) · [Properties](properties.md) · [Allocation](../memory/allocation.md) · [Language reference](README.md)
