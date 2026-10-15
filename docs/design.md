# Design

The nb language emphasises simplicity, expressiveness, readability, safety, performance, and low-level control. Its syntax is influenced by Ruby, Swift, and C, while retaining a distinct identity and its own idiosyncrasies.

## Principles

- **Simplicity:** concise, consistent syntax should make intent easy to express and type.
- **Readability:** declarations, block boundaries, and visibility should make programs understandable as they grow.
- **Safety:** static typing, controlled mutability, optional values, ownership-aware references, explicit errors, and structured concurrency prevent common mistakes.
- **Performance:** native compilation, efficient representations, and predictable memory behavior support demanding applications.
- **Expressiveness:** structs, classes, protocols, generics, closures, enums, and properties form a coherent set of abstractions.
- **Control:** programmers can progress from ordinary application code to memory and system interfaces within the same language.

## Language model

Structs provide value semantics; classes provide reference semantics. Built-in types participate in the object model. Binding mutability and object mutability are distinct. Properties express access to values; methods express operations. Protocols describe behavioral requirements. Enums remain constrained case-based types with computed properties and pure boolean validation, rather than unrestricted class-like objects.

Modules group declarations and control their visibility. Packages define the boundaries within which modules can be extended. Language behaviour remains consistent across compiler implementations.

Managed application programming and constrained freestanding programming share the language. A freestanding program must not require a mandatory garbage collector or a general-purpose managed runtime.

## Naming conventions

Objects and named types use CamelCase, as in Task, TaskService, and DivisionError. Methods use lowercase words separated by underscores, as in print_tasks and fetch_data. Predicates may end in ?; consequential methods may end in !.

Compound filenames use dashes, as in task-manager.md, control-flow.md, and task-test.nbs. nb source files use the .nbs extension.

Repositories follow the [n-os source convention](tooling/source-organization.md).

## Concise declarations

initial reads as defining initial state. Property-bound parameters reuse stored types and defaults. Initial-state declarations are public by default. Named shorthand reuses local or block names. Functions and closures explicitly declare results with ->; other declarations are void.

Global functions avoid mandatory object-oriented organisation. vargs holds additional positional arguments; collection spread supplies key/value tuples. Read-only params metadata describes signatures separately from call values.
