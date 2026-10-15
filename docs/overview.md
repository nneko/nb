# Overview

nb is a modern, statically typed, natively compiled programming language designed for expressive, safe, and high-performance software development.

It aims to combine Ruby-like expressiveness and elegance, Swift's readability, safety, speed, and power, and the low-level depth of C. nb draws from selected aspects of Ruby and Swift syntax, removing unnecessary complexity while keeping the language cohesive and simple to read, write, and understand.

nb supports software ranging from small utilities and applications to services, native libraries, embedded software, and operating-system components. Common tasks require little ceremony; ownership, concurrency, interoperability, and direct system operations remain accessible through explicit mechanisms.

Its principle is: **Expressive by default. Explicit where it matters. Powerful without unnecessary complexity.**

## Language identity

| Component | Name |
|---|---|
| Language | nb |
| Public identity | nblang |
| Toolchain | nbs |
| Source extension | .nbs |
| Manifest | nb.toml |
| Debugger | nbdb |
| Language server | nbls |
| Operating-system ecosystem | n-os |

## Programming model

Compile-time type checking and inference work with value-oriented structs, reference-oriented classes, behavioral protocols, generic types and functions, enums, closures, and computed properties. Modules and visibility define API boundaries. Optional values make absence explicit. Error contracts describe recoverable failures.

Ownership-aware memory safety, borrowing, structured concurrency, and explicit unsafe scopes support progressively lower-level programming. Detailed lifetime, aliasing, and concurrency rules are specifications in development.

nb compiles to native executables and libraries. Output formats include shared libraries, static libraries, and executables for constrained freestanding targets. The backend and intermediate representation remain implementation decisions.

## Small example

```nb
def greet(name: string) -> string do
  "Hello, \(name)"
end

print(greet("Alice"))
```

Functions use def and executable bodies use do ... end. An explicit -> declaration permits a return value, supplied by the final expression or a return statement. Without ->, the function returns no value. The complete standard-library API is a specification in development.

## Independence and interoperability

nb has its own language semantics, standard library, compiler, and execution model. Ruby compatibility is an optional interoperability capability. Native programs that do not use Ruby interoperability do not require CRuby. C ABI compatibility is the primary foreign-function boundary.

nb is developed alongside n-os and can also build standalone software. Its semantics do not depend on a particular operating-system filesystem hierarchy or package manager.

Continue with the [design principles](design.md) and [language reference](language/README.md).

## Everyday programming

Global print, print_warn, and print_debug provide configurable output. Console is a separate advanced terminal module. Structs and classes use .new(...); initial declarations define state through concise property-bound parameters.
