# Chain of Responsibility design pattern

- It allows passing of request along the chain of potential handlers until 1 of them handles the request
- it allows multiple objects to handle the request without coupling the sender class to the concrete classes of the receivers
- the chain can be composed dynamically at runtime with any handler that follows a standard handler interface

![Chain of Responsibility](../../images/chain_of_responsibility.png)

## When to use

- when your program is expected to process different kinds of requests in various ways, but the exact types of requests and their sequences are unknown beforehand
- when it’s essential to execute several handlers in a particular order
- when the set of handlers and their order are supposed to change at runtime
