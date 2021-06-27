# Command pattern
- The Command pattern aims to encapsulate method invocation, requests, or operations into a single object
- It gives us the ability to both parameterize and pass method calls around that can be executed at our discretion
- It enables us to decouple objects invoking the action from the objects that implement them, giving us a greater degree of overall flexibility in swapping out concrete classes (objects)
- idea behind the Command pattern is that it provides us a means to separate the responsibilities of issuing commands from anything executing commands, delegating this responsibility to different objects instead
## Why use the Command pattern
- By using the command pattern in our programs and applications, we are able to incorporate functionalities (such as queueing, request logging, and undo/redo operations) with a lot of ease
- This is because each request is an independent entity from other classes and objects
- therefore, we can modify or update a request without worrying about affecting other requests or objects
## Analogy
### in a restaurant
- the Client is the customer
- the Invoker is the waiter that writes the paper order that is given from the client
- the waiter then gives the paper orders as a form of command to the chefs in the kitchen
- the reciever is the chefs in the kitchen that takes the command and then prepares the meal