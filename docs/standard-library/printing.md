# Printing

print, print_warn, and print_debug are standard functions available without a module or object qualifier.

| Function | Destination | Default representation |
|---|---|---|
| print | Standard output | Ordinary text |
| print_warn | Standard error | Ordinary text |
| print_debug | Standard error | Debugging representation |

print_warn adds no automatic warning prefix. print_debug remains active in release builds unless build configuration explicitly controls it.

## Options

All three functions share labelled output options.

| Option | Default | Behaviour |
|---|---|---|
| separator | " " | Text between unformatted values |
| terminator | "\n" | Text appended after output |
| format | Omitted | Ruby-compatible printf format string |

```nb
print("Hello, world!")
print("Alice", 30)
print("Alice", 30, separator: ": ")
print("Loading...", terminator: "")
print_warn("Task not found")
print_debug(task)
```

Without format, values use ordinary or debugging text representations and are joined using separator. terminator is then appended, adding a newline by default.

## Format strings

format is the format string itself, not a boolean mode selector. Formatting follows Ruby printf conventions.

```nb
print("Alice", 3, format: "%s has %d tasks")
print(19.95, format: "Price: %.2f")
print(7, format: "Item %03d")
print(50, format: "%d%% complete")
```

The format controls conversion, flags, width, precision, and value combination. separator has no effect when format is supplied. terminator still applies; a newline within format does not suppress it.

Invalid formats and incompatible arguments report an error rather than silently producing misleading output. Mapping nb types to conversion directives, Ruby-compatible named-format arguments, and the diagnostic/error contract are specifications in development. Collection spread remains positional key/value tuples and does not create keyword arguments.

## Streams and terminals

Printing writes to standard streams and supports redirected output. Advanced colours, cursor operations, keyboard modes, and screen interfaces belong to the Console module.

## Specification in development

Complete callable signatures and option binding, format type mappings, named-format value sources, encoding, buffering, stream failures, format error types, and build controls for debug output.

[Console](console.md) · [I/O](io.md) · [Arguments](../language/arguments.md) · [Global namespace](../language/namespaces.md) · [Standard library](README.md)
