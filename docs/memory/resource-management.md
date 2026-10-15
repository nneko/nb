# Resource management

Scope-exit cleanup releases resources deterministically.

## Syntax and examples

```nb
let file = File.open("example.txt")

defer do
  file.close()
end

let contents = file.read()
```

## Semantics

defer provides deterministic scope-exit cleanup. Error handling also supplies ensure. Ownership-oriented cleanup syntax is a specification in development.

## Rules and constraints

File ownership and failure contracts are specifications in development.

## To be defined

To be defined: Multiple-defer ordering, exits and unwinding, cleanup failures, cancellation, ownership-oriented constructs, and interaction between ensure and defer.

## Related specifications

[Errors](../language/errors.md) · [Ownership](ownership.md) · [Filesystem](../standard-library/filesystem.md)

[Section navigation](README.md) · [Specification status](../status.md)
