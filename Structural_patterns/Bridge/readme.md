# Bridge pattern

- It divides business logic or huge class into separate class hierarchies that can be developed independently
  - one of these hierarchies (often called `Abstraction`) will get a reference to an object of the 2nd hierarchy (`Implementation`)
  - the abstraction will be able to delegate some of its calls to the implementations object
    - since all implementations will have a common interface and would be interchangeable inside the abstraction

## Why use the Bridge pattern

- it is useful for
  - dealing with cross-platform apps
  - supporting multiple types of database servers
  - working with serveral API providers of a certain kind
    - e.g.: cloud platforms, social networks
