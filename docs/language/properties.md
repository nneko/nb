# Properties

Stored members hold state. Computed properties use computed and are read without method-call parentheses.

## Syntax and examples

```nb
computed full_name: string do
  "\(first_name) \(last_name)"
end

public computed balance: decimal do
  get do
    balance_value
  end
  protected set(value: decimal) do
    balance_value = value
  end
end

account.balance
```

## Semantics

A simple computed body supplies the property value. Explicit get and set accessors support controlled read and write behavior. The task-manager demonstrates a computed completed? boolean property. Computed properties remain distinct from methods.

## Rules and constraints

An accessor may narrow the property's visibility but cannot broaden it. A public property with a protected setter is shown. A private property with a public accessor would violate that visibility constraint. Members of classes and structs default to private.

## To be defined

To be defined: Setter assignment grammar, accessor default visibility, evaluation/caching rules, property overrides, observer mechanisms if any, and writable-property interaction with borrowing.

## Related specifications

[Modules and visibility](modules.md) · [Classes](classes.md) · [Enums](enums.md)

[Section navigation](README.md) · [Specification status](../status.md)

## Initial values

Stored defaults supply omitted memberwise and property-bound arguments. An explicit bound-parameter default takes precedence. Computed properties are not memberwise construction inputs. See [initial state](initial-state.md).
