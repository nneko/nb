# Task manager

A task-management application demonstrating classes, structs, protocols, enums, computed properties, optional values, and explicit error handling.

## Repository

```text
task-manager/
├── README.md
├── .gitignore
├── nb.toml
├── source/
│   ├── main.nbs
│   ├── models.nbs
│   └── services.nbs
└── tests/
    └── unit/
        └── task-test.nbs
```

The repository follows the n-os source convention. Objects use CamelCase, methods use underscores, and compound filenames use dashes.

## Build and run

From the project root:

```sh
nbs check
nbs test
nbs build
nbs run source/main.nbs
```

The manifest schema, test discovery, and assertion API are specifications in development.

[Application walkthrough](../../docs/examples/task-manager.md)
