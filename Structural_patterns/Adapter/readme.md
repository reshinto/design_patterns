# Adapter design pattern
- original definition
  - Convert the interface of a class into another interface clients expect
  - Adapter lets classes work together that couldn't otherwise because of incompatible interfaces
- Adapters help mitigate incompatibilities between interfaces by adapting 1 interface to another
## When to use
- Make old component usable in a new system
- Make an "off-the-shelf" solution usable in a system that is not fully compatible
- example
  - if we are using a class, and a consumer is using the methods
  - then we need to switch from the current class to a better class
    - the better class offers a different interface and will require the client code to be refactored to use it
    - migration will not be easy, especially if it is a large enterprise app where methods are deeply integrated and extensively used
  - will need a decoupled solution which is easy to implement and does not involve refactoring as much as possible
    - by using the adapter pattern, refactoring can be minimised
    - done by maping methods from better class to how our clients expects
  - the adapter helps the consumer adapt to a new interface by using the pattern
## Summary
- the adapter pattern is used to create a bridge between 2 different interfaces
- removes incompatibilities between the interfaces
- prevents or minimizes refactoring client application code
- lets you build packages with an opinionated API, with custom adapters for maximum compatibility
