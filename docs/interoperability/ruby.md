# Ruby compatibility

Ruby compatibility is optional and separate from native nb semantics.

## Syntax and examples

```ruby
#lang ruby

class Greeting
  def hello(name)
    puts "Hello #{name}"
  end
end
```

## Semantics

Compatibility source may use #lang ruby. Ruby integration covers .rb source files, CRuby, gems, and bridge behaviour. Ruby source must preserve Ruby semantics rather than being treated as ordinary statically typed nb. A bridge may expose selected Ruby libraries and gems.

## Rules and constraints

Native nb programs that do not use Ruby interoperability do not require CRuby. Compatibility sources use Ruby interpolation and function syntax.

## To be defined

To be defined: .rb dispatch and mode selection precedence, supported Ruby/CRuby versions, bridge API, type conversion, lifetime management, error conversion, threading, gem loading, native extensions, and deployment.

## Related specifications

[FFI](ffi.md) · [Bindings](bindings.md) · [Runtime](../platform/runtime.md)

[Section navigation](README.md) · [Specification status](../status.md)
