# Creational Patterns: Abstract Factory
## Allows you to create families of related objects without specifying a concrete class for each object
### Analogy:
* Imagine that you're a clothing designer
* You need to build types of clothing
  * e.g.: shirts, sweaters, jeans
* You also need sizes of clothing
  * e.g.: petites, regular, tall
* To build these with Abstract Factory pattern
  1. create an interface to build the clothing type (e.g.: sweater)
  2. create another interface to build the size (e.g.: petites)
  * These 2 interfaces will work together to generate a (petite-sized sweater)
### Coding terms:
  * Imagine you're creating a "submit" button that will be used on windows and mac operating systems
  * The button is the same object with the same functionality
    * only with a different class (Windows or Mac) depending on the operating system
