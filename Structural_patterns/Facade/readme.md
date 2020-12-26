# Facade design pattern
- original definition
  - provide a unified interface to a set of interfaces in a subsystem
  - it defines a higher-level interface that makes the subsystem easier to use
- basically, the client only has to talk to the facade, which then delegates all of the responsibilities of knowing how to use the various potentially complicated sybsystems to it
  - the facade does all the heavy lifting
  - and the client just has to know the interface of the facade
## Why use
- make a library easier to use, understand, and test
  - since the facade has convenient methods for common tasks
- reduce dependencies of outside code on the inner workings of a library
  - allowing more flexibility in developing the system
- wrap a poorly designed collection of APIs with a single well-designed API
