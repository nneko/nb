# Systems programming

Borrowing, ownership transfer, references, and unsafe scopes provide explicit control over memory access. These fragments use an application-defined Buffer type and process function:

```nb
def inspect(value: borrow Buffer) do
  print(value.length)
end

def modify(value: borrow mut Buffer) do
  value.clear()
end

def consume(value: take Buffer) do
  process(value)
end

unsafe do
  let pointer = address(buffer)
end
```

These are independent syntax examples, not a complete freestanding executable. Freestanding execution must not require a mandatory collector or general-purpose managed runtime. Standard printing availability in freestanding profiles is a specification in development.

To be defined: Buffer, allocation, pointer operations, lifetime checks, target profile, entry point, library subset, and build/link contracts before creating a complete systems program.

[Memory](../memory/README.md) · [Freestanding](../platform/freestanding.md) · [Example navigation](README.md)
