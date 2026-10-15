# Syntax

nb source files use the .nbs extension. Declarations use readable keywords and explicit block delimiters. Every source file belongs to an implicit or explicit module.

## Syntax and examples

```nb
# A comment
let name: string = "Alice"
var count = 0

def greet(name: string) -> string do
  "Hello, \(name)"
end

numbers.each do |number|
  print(number)
end
numbers.map({ |number| number * 2 } -> integer)
names.map({ |name| name.upcase() } -> string)
```

## Semantics

Type annotations follow a colon. Return annotations follow ->. Executable function bodies require do ... end; modules, classes, structs, enums, and control-flow forms use their shown declaration-specific block syntax. Blocks may use do ... end or the short brace form. Identifiers may carry a predicate ? suffix or consequential ! suffix.

## Rules and constraints

A declaration signature in a protocol is not an executable function body. The ! suffix is a naming convention, distinct from prefix logical negation.

## To be defined

To be defined: Formal lexical grammar, identifier character classes, reserved-word set, escapes, separators, line continuation, expression grammar, and ambiguity resolution. The formal grammar is a specification in development.

## Related specifications

[Functions](functions.md) · [Operators](operators.md) · [Modules](modules.md)

[Section navigation](README.md) · [Specification status](../status.md)

## Initial state and results

Initial state uses def initial(...) state ... end and defaults to public. Functions and closures require -> Type to return a value; otherwise final expression values are discarded. Brace closures place -> Type after the closing brace. See [initial state](initial-state.md) and [closures](closures.md).
