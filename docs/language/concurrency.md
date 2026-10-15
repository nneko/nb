# Concurrency

nb provides async functions, await, and structured concurrency. Typed channels, mutexes, and atomic values support communication and synchronisation.

## Syntax and examples

```nb
async def fetch_data(url: string) -> string do

  let response = await Http.get(url)

  response.body

end
```

```nb
concurrent do

  let first = spawn fetch_data(
    "https://example.com/first"
  )

  let second = spawn fetch_data(
    "https://example.com/second"
  )

  let results = [
    await first,
    await second
  ]

  print(results)

end
```

```nb
channel<string>
mutex<Counter>
atomic<integer>
```

## Semantics

async marks asynchronous functions. await is used for an asynchronous result. concurrent introduces the structured concurrency form; spawn starts work within the example scope. The concurrency safety model aims to prevent unsynchronised mutable access across execution contexts.

## Rules and constraints

Scheduling, thread mapping, cancellation, scope completion, channel buffering, mutex operations, and atomic memory ordering are specifications in development. The complete Http API is also in development.

## To be defined

To be defined: Task lifetime and scope-exit behavior, cancellation, error aggregation, isolation/transfer checking, executors, async entry points, channel operations, mutex rules, atomic ordering, and freestanding availability.

## Related specifications

[Library concurrency](../standard-library/concurrency.md) · [Borrowing](../memory/borrowing.md) · [Runtime](../platform/runtime.md)

[Section navigation](README.md) · [Specification status](../status.md)
