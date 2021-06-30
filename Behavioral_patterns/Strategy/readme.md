# Strategy design pattern

## Structure

![Strategy](../../images/strategy.png)

1. The Context maintains a reference to one of the concrete strategies and communicates with this object only via the strategy interface.

2. The Strategy interface is common to all concrete strategies.

   - It declares a method the context uses to execute a strategy.

3. Concrete Strategies implement different variations of an algorithm the context uses.

4. The context calls the execution method on the linked strategy object each time it needs to run the algorithm.

   - The context doesn’t know what type of strategy it works with or how the algorithm is executed.

5. The Client creates a specific strategy object and passes it to the context.
   - The context exposes a setter which lets clients replace the strategy associated with the context at runtime.
