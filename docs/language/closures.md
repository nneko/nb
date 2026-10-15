# Closures

Closures enclose executable code and can receive parameters. Their explicit return annotation follows the closing brace.

## Returned values

```nb
let double = { |value: integer| value * 2 } -> integer

let doubled = numbers.map(
  { |value| value * 2 } -> integer
)
```

-> integer declares a result. The final expression supplies it and must be compatible with that type. Parameters may obtain types from context or carry explicit annotations. Parameter inference does not infer a return declaration.

Parentheses can group the complete closure expression.

```nb
let square = ({ |value: integer| value * value } -> integer)
```

## Void closures

```nb
numbers.each { |value| print(value) }

numbers.each do |value|
  print(value)
end
```

Without ->, a closure returns no value, and a final expression value is discarded. A closure required to produce a value must explicitly declare its result.

## Parameters

Closure parameters support defaults and a final variadic marker. The shared argument rules apply. Names resolve lexically.

## Specification in development

Return annotations for long do ... end blocks and symbol-to-method shorthand, callable invocation grammar and types, capture modes, and captured-value lifetimes. Brace closures provide the defined explicit-return form.

[Functions](functions.md) · [Arguments](arguments.md) · [Lifetimes](../memory/lifetimes.md) · [Language reference](README.md)
