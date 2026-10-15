# Task manager

A task-management application combining models, a service, an entry point, and a unit test. It demonstrates initial state, property bindings, memberwise struct construction, explicit results, closures, errors, optional values, and global printing.

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

The [complete project](../../examples/task-manager/README.md) follows the n-os source convention. Objects use CamelCase, methods use underscores, and compound filenames use dashes.

## Manifest

The manifest is illustrative; its schema is a specification in development.

```toml
[package]
name = "task-manager"
version = "0.1.0"
description = "A sample task manager written in nb"

[build]
entry = "source/main.nbs"
```

## Models

Task uses initial with state, and @id binds before its body. Ordinary title and status parameters initialise differently named fields. Position uses automatic memberwise initialisation.

```nb
module Models

  public enum Status

    case pending
    case active
    case completed

    public computed label: string do

      match self
        case .pending then "Pending"
        case .active then "Active"
        case .completed then "Completed"
      end

    end

  end

  public protocol Identifiable

    def identifier -> string

  end

  public struct Position

    public let x: float
    public let y: float

    public computed distance: float do
      (x * x + y * y).sqrt()
    end

  end

  public class Task < Identifiable

    private let id: string

    private var title_value: string
    private var status_value: Status = .pending

    def initial(
      @id,
      title: string,
      status: Status = .pending
    ) state
      self.title_value = title
      self.status_value = status

    end

    public def identifier -> string do
      id
    end

    public computed title: string do

      get do
        title_value
      end

      protected set(value: string) do
        title_value = value
      end

    end

    public computed status: Status do
      status_value
    end

    public computed completed?: boolean do
      status_value == .completed
    end

    public def complete! do
      status_value = .completed
    end

    public def describe -> string do
      "\(title) [\(status.label)]"
    end

  end

end
```

## Service

TaskService has an empty initial body and a defaulted tasks property. Named shorthand resolves local parameters. The find closure explicitly declares -> boolean.

```nb
import Models from "./models.nbs"

module Services

  public enum TaskError

    case not_found
    case invalid_title

  end

  public class TaskService

    private var tasks: sequence<Models::Task> = []

    def initial() state
    end

    public def add(
      id: string,
      title: string
    ) -> Models::Task raises TaskError do

      if title.empty?
        raise TaskError.invalid_title
      end

      let task = Models::Task.new(
        id:,
        title:
      )

      tasks.push(task)

      task

    end

    public def find(
      id: string
    ) -> Models::Task? do

      tasks.find(
        { |task| task.identifier == id } -> boolean
      )

    end

    public def complete!(
      id: string
    ) raises TaskError do

      let task = find(id)

      if task.nil?
        raise TaskError.not_found
      end

      task.unwrap().complete!

    end

    public computed count: integer do
      tasks.length
    end

    public def all -> sequence<Models::Task> do
      tasks.copy()
    end

  end

end
```

## Entry point

The application uses global print, handles errors, and reports completion through ensure. Its async entry point requires no concurrent work.

```nb
import Models from "./models.nbs"
import Services from "./services.nbs"

module Application

  private def print_tasks(
    tasks: sequence<Models::Task>
  ) do

    for task in tasks
      print(task.describe())
    end

  end

  public async def main do

    print("Welcome to nb!")

    let service = Services::TaskService.new()

    try

      let first = service.add(
        id: "task-001",
        title: "Design the nb language"
      )

      let second = service.add(
        id: "task-002",
        title: "Implement the compiler"
      )

      service.complete!(first.identifier)

      print(
        "Total tasks: \(service.count)"
      )

      print_tasks(service.all())

    handle error: Services::TaskError

      print(
        "Task operation failed: \(error)"
      )

    ensure

      print("Application finished.")

    end

  end

end
```

## Unit test

The test checks the transition to completed. Test discovery and assert APIs are specifications in development.

```nb
import Models from "../../source/models.nbs"

module TaskTests

  public def test_task_completion do

    let task = Models::Task.new(
      id: "task-001",
      title: "Test task"
    )

    assert(task.completed? == false)

    task.complete!

    assert(task.completed? == true)

  end

end
```

## Build and run

From the project root:

```sh
nbs check
nbs test
nbs build
nbs run source/main.nbs
```

Expected output:

```text
Welcome to nb!
Total tasks: 2
Design the nb language [Completed]
Implement the compiler [Pending]
Application finished.
```

## Specification in development

Manifest schema, entry-point invocation, complete conformance grammar, sequence API and copy depth, error propagation, optional failures, assertion API, and test discovery. The compiler and runtime implementation are not included.

[Initial state](../language/initial-state.md) · [Arguments](../language/arguments.md) · [Closures](../language/closures.md) · [Printing](../standard-library/printing.md) · [Examples](README.md)
