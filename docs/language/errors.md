# Errors

Functions declare explicit error contracts. raise reports a failure; try, handle, and ensure express recovery and cleanup.

## Syntax and examples

```nb
def divide(
  a: float,
  b: float
) -> float raises DivisionError do

  if b == 0.0
    raise DivisionError.zero_division
  end

  a / b

end
```

```nb
try

  let result = divide(10.0, 2.0)

  print(result)

handle error: DivisionError

  print("Division failed")

ensure

  print("Operation complete")

end
```

```nb
let file = File.open("example.txt")

defer do
  file.close()
end

let contents = file.read()
```

## Semantics

A raises clause names the function's error contract.

## Rules and constraints

Error contracts are explicit. The failure contracts for File.open, read, and close are specifications in development.

## To be defined

To be defined: Propagation and effect-checking rules, multiple error types, handler selection, re-raising, ensure/defer ordering, cleanup errors, cancellation interaction, and foreign-boundary failure conversion.

## Related specifications

[Resource management](../memory/resource-management.md) · [Functions](functions.md) · [FFI](../interoperability/ffi.md)

[Section navigation](README.md) · [Specification status](../status.md)
