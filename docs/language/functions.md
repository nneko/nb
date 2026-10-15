# Functions

Functions use def, parameters, and do ... end bodies. They can be called without an object or explicit module qualifier.

## Declarations

```nb
def greet(name: string = "Guest") -> string do
  "Hello, \(name)"
end

def show_message(message: string) do
  print(message)
end

def even?(value: integer) -> boolean do
  value % 2 == 0
end
```

Parameterless declarations may omit parentheses. Predicates ending in ? return boolean. A ! suffix marks consequential behaviour by convention; it is not an operator.

## Return declarations

-> Type explicitly declares a return value. The final expression supplies that value and is checked against the declared type. A return statement may supply a result earlier; a return statement in the body is not mandatory.

```nb
def square(value: integer) -> integer do
  value * value
end
```

Without ->, a function returns no value: void, not nil. A value produced by its final expression is discarded. A void call cannot be used where a value is required.

```nb
def calculate_and_discard(value: integer) do
  value * value
end

calculate_and_discard(4)
# Invalid: let result = calculate_and_discard(4)
```

The compiler checks declared results; it does not infer a return declaration. Functions and closures follow the same rule. Each normally completing path in a value-returning callable must supply a compatible result.

## Parameters

Functions, methods, closures, and initial-state declarations support defaults. A trailing ... captures additional positional arguments in vargs. [Arguments](arguments.md) defines binding, labels, shorthand, defaults, and spread.

## Executable bodies

Ordinary functions require do ... end. Protocol requirements declare signatures without executable bodies. Initial-state declarations use the special def initial(...) state ... end form.

## Specification in development

Callable types, complete overload resolution, explicit return-statement grammar, and callable lifetime representation.

[Arguments](arguments.md) · [Closures](closures.md) · [Initial state](initial-state.md) · [Protocols](protocols.md) · [Language reference](README.md)
