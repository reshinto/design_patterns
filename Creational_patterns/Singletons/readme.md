# Singletons
- Objects that can only have a single instance, with a single point of access
- Useful for maintaining a central state, where all clients need to access and operate on a common resource
## Javascript
### The Node.js module system provides a basic framework for implementing a rudimentary singleton
```javascript
let num1 = 0;
module.exports = {
  add: (num) => num1 + num,  // module 1
  subtract: (num) => num1 - num,  // module 2
};
```
#### Creating a singleton with ES5
- When module is imported, only a single instance is created and referred to
  - This is because the module system caches the module the moment it is accessed by using a require statement
  - Therefore, regardless of the number of times imported, the same instance is referred and is will be accessed via the same cached and common instance
  - However, although this behavior behaves like a singleton, it is technically just an instance of the module that is cached upon first access
#### Creating a singleton with ES6 class
- Normal way of exporting and importing Singletons defined with ES6 class with not behave like a singleton
  - as they do not share the same point of access
- Need to create an instance and export the instance to make it behave like a singleton
