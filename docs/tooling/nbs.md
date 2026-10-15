# nbs CLI

nbs brings project creation, compilation, checking, testing, formatting, and dependency management into a single command-line interface.

| Command | Purpose |
|---|---|
| nbs init | Initialize an nb project |
| nbs run source/main.nbs | Compile and execute an application |
| nbs build | Compile a project or target |
| nbs check | Semantic and type checking |
| nbs test | Execute project tests |
| nbs format | Format source |
| nbs add http | Add the example language dependency |

In nbs add http, http is an example dependency name. Package registries and dependency resolution are specifications in development.

nbs manages nb projects and language dependencies. It does not replace n-os pkg, pkgr, or bldr.

## To be defined

Define flags, command grammar, project discovery, error/exit codes, stdout/stderr behavior, versioning, offline operation, dependency sources, target selection, and configuration precedence.

[Build](build.md) · [Packages](packages.md) · [n-os integration](../platform/n-os.md) · [Tooling navigation](README.md)
