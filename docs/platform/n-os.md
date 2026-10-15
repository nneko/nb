# n-os integration

nb integrates with the n-os development ecosystem and supports standalone compilation. Its language semantics remain independent of operating-system packaging and deployment.

nbs manages nb project operations and language dependencies. It does not replace pkg, pkgr, or bldr. The n-os build system may invoke the compiler; package construction, authentication, repository publication, and system composition remain governed by their existing specifications.

```text
nb source → nbs compiler → native executable/library
          → n-os package build → authenticated package
          → n-os package management → system composition
```

Build hosts, controlled targets, package construction, and system composition retain distinct responsibilities. nb integration follows these boundaries and the established source conventions.

Language semantics must not depend on the operating-system filesystem hierarchy, package manager, or runtime.

## To be defined

Specify toolchain invocation, controlled target profiles, build-host separation, package metadata integration, reproducible builds, and interface availability. No existing n-os package or system contract is redefined by this document.

[Source organization](../tooling/source-organization.md) · [nbs](../tooling/nbs.md) · [Targets](targets.md) · [Platform navigation](README.md)
