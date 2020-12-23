# Decorator design pattern
- original definition
  - Attach additional responsibilities to an object dynamically
  - decorators provide a flexible alternative to sub classing for extending functionality
- a good way to define pluggable behaviors and features for clients that do not alter their original function but add extra abilities
- also known as a wrapper pattern
  - when used with functions, a decorator ingests a function and returns back a function
    - this way it behaves as a higher order function
- example
  - the react framework uses the concept of higher order components
    - which results in a component gaining extra abilities and functionality
## Summary
- the decorator pattern, ingests a function and returns back a function
- decorators can be used to add features and function to existing objects dynamically
- implemented as higher order functions
### Javascript
- the TC39 has proposed the decorator (@decorator) syntax for use with classes and class methods
- until the format is released, the decorator syntax can be implemented using the babel complier
### Python
- the decorator design pattern is NOT the same as the python decorator / function wrapper
