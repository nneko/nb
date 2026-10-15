# Packages

A package organizes source modules and language dependencies. nb.toml is the project manifest, at the package root.

## Syntax and examples

```toml
[package]
name = "task-manager"
version = "0.1.0"
description = "A sample task manager written in nb"

[build]
entry = "source/main.nbs"
```

## Semantics

Production source belongs in source/. Public interface artifacts belong in interfaces/ when needed. Package boundaries matter to module extension authorization. nbs manages language project operations and dependencies; operating-system package construction and distribution retain their own responsibilities.

## Rules and constraints

Packages follow the n-os source convention. Directories are present when their contents are needed. Generated output belongs in build/. Dependency resolution and publication contracts are specifications in development.

## To be defined

To be defined: Normative manifest schema, package identity rules, dependency version syntax, resolution/locking, registries, workspace behavior, entry discovery, and package interface/export mechanics.

## Related specifications

[Modules](modules.md) · [Source organization](../tooling/source-organization.md) · [Package tooling](../tooling/packages.md)

[Section navigation](README.md) · [Specification status](../status.md)
