# Reflection

params provides read-only metadata for a callable's complete parameter signature. It describes the declaration rather than values from a particular call.

## Parameter descriptors

Descriptors include parameter name, external label, declared type, whether a default exists, and whether the parameter is variadic. Property-bound parameters can identify their corresponding property.

```nb
def announce(prefix: string = "Update:", ...) do
  for value in vargs
    print(prefix, value)
  end
end
```

The signature describes prefix and the variadic parameter associated with vargs. Metadata is accessed through reflection on the callable, rather than through an implicit params variable in every body.

| Facility | Contents |
|---|---|
| vargs | Additional positional values from an invocation |
| params | Read-only descriptors for the complete signature |

Metadata can report a default's existence without evaluating it. Defaults execute only when needed by an omitted argument. Read-only metadata does not permit runtime signature changes.

## Specification in development

Reflection access syntax, descriptor types, metadata availability, default-expression inspection, and generic or overloaded callable metadata.

[Functions](functions.md) · [Arguments](arguments.md) · [Language reference](README.md)
