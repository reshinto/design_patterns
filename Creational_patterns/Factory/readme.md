# Factory
- it is an interface for creating an object which lets subclasses decide which class to instantiate
- also know as the virtual constructor pattern
## Analogy
- assume a phone in an elementary form has
  - a model name, processor type, amount of RAM, dimensions, screen resolutions
- a phone factory can manufacture all kinds of phones
  - only need to supply a combination of feature attributes to get the job done
  - once a combinations of specs listed as model A, B, and C are available
    - do not need to specify the specs again
- in conclusion, the factory pattern allows generation of preconfigured custom objects easily
  - without the need to pass in contructor options each time
## Summary
- factory pattern provides an interface for constructing pre-configured objects
- code is cleaner and resilient
- pattern is useful when writing packages for public use
- allows an easy to understand interface to the package functions
