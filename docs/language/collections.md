# Collections

nb distinguishes indexed, keyed, fixed, dynamic, homogeneous, and heterogeneous structures explicitly.

## Syntax and examples

```nb
let coordinates: array<float, 3> = [1.0, 2.0, 3.0]
let numbers = [1, 2, 3, 4, 5]
let names: sequence<string> = ["Alice", "Bob", "Charlie"]
let values: list = [10, "hello", true]
let unique = set(1, 2, 3, 4)
let scores: map<string, integer> = {
  "Alice" => 95,
  "Bob" => 88
}
let user: collection = {
  name: "Alice",
  age: 30,
  active: true
}
let point = (x: 10, y: 20)
let indexed_values = [10, 20, 30, 40]
let portion: slice<integer> = indexed_values[1..3]
```

## Semantics

| Construct | Semantics |
|---|---|
| array<T, N> | Fixed-size homogeneous indexed collection |
| sequence<T> | Dynamically sized homogeneous indexed collection |
| list | Heterogeneous indexed collection |
| set | Homogeneous unique values |
| map<K, V> | Homogeneous keyed collection |
| collection | Heterogeneous keyed collection |
| tuple | Fixed-structure grouped value |
| slice<T> | View into a suitable indexed collection |

Indexing is bounds-checked. Negative indexing is supported for appropriate indexed collections. Slices are views, so their validity interacts with ownership and lifetimes.

## Rules and constraints

A heterogeneous keyed collection does not implicitly expose numeric indexes. Homogeneous collections must respect their declared element/key/value types. Array length coercion and heterogeneous promotion rules are to be defined.

## To be defined

To be defined: Range endpoint inclusion, negative-index domain, invalid-index failure, set/hash constraints, iteration order, tuple typing, slice mutability and lifetime, collection copy semantics, and full library APIs.

## Related specifications

[Types](types.md) · [Generics](generics.md) · [Borrowing](../memory/borrowing.md) · [Library collections](../standard-library/collections.md)

[Section navigation](README.md) · [Specification status](../status.md)

## Argument spread

Postfix ... spreads lists, sequences, and arrays as positional elements. A collection supplies positional (key, value) tuples, never named arguments. See [arguments](arguments.md).
