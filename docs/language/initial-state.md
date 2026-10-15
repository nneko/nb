# Initial state

initial defines the initial state of a struct or class. The special .new(...) method constructs an instance.

## Declaration

```nb
class Task

  private let title: string
  private let priority: integer = 0

  def initial(@title, @priority) state
  end

end

let task = Task.new(title: "Write documentation")
```

Initial-state declarations use state ... end instead of do ... end. They are public by default; private or protected explicitly restricts access. initial has no ordinary return declaration. .new(...) produces the constructed value or object reference.

## Property-bound parameters

@name binds a parameter to the corresponding declared instance property. Its type comes from that property. An unknown property or indeterminate type is an error.

Bindings occur before the state body executes. An immutable property initialised by a bound parameter cannot be assigned again.

Inputs without a direct property relationship use ordinary parameters.

```nb
class Task

  private let title: string
  private let priority: integer

  def initial(@title, urgent: boolean = false) state
    self.priority =
      if urgent
        10
      else
        0
      end
  end

end
```

## Defaults

A bound parameter inherits its property's default unless it declares an explicit parameter default. The explicit default takes precedence for that initialiser.

```nb
class Task

  private let title: string
  private let priority: integer = 0

  def initial(@title, @priority = 2) state
  end

end
```

Omitting priority uses 2 here; without the parameter default, it uses the property default of 0. Defaults evaluate lazily, afresh for each construction that needs them. An overridden default is not evaluated merely to be replaced. The common restrictions on default expressions apply.

## Automatic struct initialisation

A struct without an explicit initial receives a public memberwise initialiser for its public stored properties. Property defaults supply omitted arguments.

```nb
struct Point

  public let x: float = 0.0
  public let y: float = 0.0
  private let label: string = ""

end

let origin = Point.new()
let offset = Point.new(x: 10.0)
```

Private and protected stored properties require defaults for this automatic form; otherwise an explicit initial is required. They do not become public construction parameters. Computed properties are not memberwise inputs. An explicit initial replaces the automatic form.

Every stored property must have an initial value before construction completes. Automatic class initialisation is a specification in development; example classes declare initial explicitly.

## Specification in development

Initialiser overloads, inheritance and delegation, failure during construction, complete definite-initialisation analysis, and lifetimes of partially initialised instances.

[Structs](structs.md) · [Classes](classes.md) · [Arguments](arguments.md) · [Properties](properties.md) · [Language reference](README.md)
