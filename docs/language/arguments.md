# Arguments

Parameters declare callable inputs. Arguments provide their values. Functions, methods, closures, and initial-state declarations share these rules.

## Defaults

```nb
def greet(name: string = "Guest") -> string do
  "Hello, \(name)"
end

greet()
greet(name: "Alice")
```

A default is evaluated lazily, only when its argument is omitted, and afresh on every call that omits it. An explicitly supplied value, including nil for an optional parameter, does not trigger the default. Defaults must be compatible with their parameter types.

Default expressions resolve names in the declaration scope, not the caller's scope. They cannot reference other parameters of the same declaration.

Expressions evaluate left to right. Parameters are processed in declaration order, using supplied values or evaluating omitted defaults. The precise interaction between source-order evaluation of out-of-order labelled arguments and declaration-order default evaluation is a specification in development.

## Positional binding

Required parameters may follow defaulted parameters. Binding reserves arguments for required parameters, following Ruby-style positional rules.

```nb
def example(first: integer = 10, second: integer) do
  print(first, second)
end

example(5)             # first = 10, second = 5
example(2, 5)          # first = 2, second = 5
example(second: 5)     # first = 10, second = 5
```

Enough positional arguments are reserved for trailing required parameters. Remaining arguments bind to defaulted parameters in declaration order. Missing defaulted arguments use their defaults. Labels identify parameters explicitly and are optional when binding is unambiguous.

Binding follows parameter structure rather than guessing from argument types. Multiple valid interpretations require explicit labels. Duplicate parameter bindings, missing required arguments, and unmatched named arguments are errors.

## Named-argument shorthand

```nb
let title = "Write documentation"
let priority = 2
let task = Task.new(title:, priority:)
```

name: means name: name. Lookup is limited to local and block scope. It does not implicitly resolve to properties, module members, or global declarations. Unknown or ambiguous shorthand names are errors.

## Variadic arguments

A final ... parameter marker introduces the implicit local list vargs. It contains only additional positional arguments. Declared parameters are excluded whether supplied positionally, by name, or through defaults.

```nb
def announce(prefix: string = "Update:", ...) do
  for value in vargs
    print(prefix, value)
  end
end

announce(prefix: "Status:", "Ready", 3, true)
```

Here vargs contains the three values "Ready", 3, and true. With no additional arguments it is empty. It may hold heterogeneous values. A variadic callable cannot redeclare vargs as another parameter or local variable in the same scope. Elsewhere, vargs is an ordinary identifier. A declaration has at most one variadic marker, in final position.

## Spread

Postfix ... expands a list, sequence, array, or collection into positional arguments.

```nb
def inspect(...) do
  for value in vargs
    print_debug(value)
  end
end

let values: list = ["Ready", 3, true]
inspect(values...)

def forward(...) do
  inspect(vargs...)
end
```

Lists, sequences, and arrays supply their elements in iteration order. A collection supplies one (key, value) tuple per entry, in its iteration order.

```nb
let details: collection = {
  name: "Alice",
  age: 30
}

inspect(details...)
```

Collection keys do not become argument labels. Each entry remains a positional tuple. Key representation and collection iteration order are specifications in development. Receivers validate any expected keys explicitly.

## Specification in development

Complete ambiguity analysis across overloads, defaults, labelled arguments, and variadic capture; dynamic arity checks for spread sources; precise scheduling of out-of-order labelled calls.

[Functions](functions.md) · [Collections](collections.md) · [Reflection](reflection.md) · [Initial state](initial-state.md) · [Language reference](README.md)
