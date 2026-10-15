# Source organization

nb repositories follow the n-os source convention.

| Directory | Responsibility |
|---|---|
| source/ | Production source code |
| interfaces/ | Public interfaces |
| tests/ | Automated and interactive tests, including fixtures |
| resources/ | Component-owned non-code assets |
| external/ | Externally owned source and build inputs |
| aux/ | Auxiliary programs and source |
| spikes/ | Experiments and prototypes |
| docs/ | Authoritative documentation |
| build/ | Generated build output |

Directories are present when their contents are needed. tests/ may contain unit/, integration/, e2e/, fixtures/, and interactive/. Generated output belongs in build/.

nb.toml resides at the project root. README.md describes the component. LICENSE states licensing terms. Makefile contains build integration when required. .gitignore excludes generated and local-only files.

## Naming conventions

Objects and named types use CamelCase, as in Task, TaskService, and DivisionError. Methods use lowercase words separated by underscores, as in print_tasks and fetch_data. Predicates may end in ?; consequential methods may end in !.

Compound filenames use dashes, as in task-manager.md, control-flow.md, and task-test.nbs. nb source files use the .nbs extension.

[Task-manager repository](../../examples/task-manager/README.md) · [Packages](../language/packages.md) · [Tooling](README.md)
