# Control flow

Conditionals, loops, and matching express decisions and repeated work. Conditional expressions can produce values.

## Syntax and examples

```nb
if age >= 18
  print("Adult")
else
  print("Minor")
end
```

```nb
let category =
  if age >= 18
    "Adult"
  else
    "Minor"
  end

for number in numbers
  print(number)
end

while counter < 10
  counter += 1
end

match status
  case .pending then "Pending"
  case .active then "Active"
  case .completed then "Completed"
end
```

## Semantics

if/else selects branches; for iterates over a collection; while repeats according to its condition. match selects among enum cases and other suitable patterns. Conditional unwrapping uses if let as documented under types.

## Rules and constraints

Boolean expressions use boolean-compatible operands. Complete pattern grammar, exhaustiveness checking, and branch result typing are specifications in development.

## To be defined

To be defined: Pattern grammar, exhaustiveness, guards, loop control operations, conditional result unification, condition compatibility, and evaluation order.

## Related specifications

[Types](types.md) · [Enums](enums.md) · [Errors](errors.md)

[Section navigation](README.md) · [Specification status](../status.md)
