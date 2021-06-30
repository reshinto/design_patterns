# State design pattern

## Structure

![State](../../images/state.png)

1. Context stores a reference to one of the concrete state objects and delegates to it all state-specific work.

   - The context communicates with the state object via the state interface.
   - The context exposes a setter for passing it a new state object.

2. The State interface declares the state-specific methods.

   - These methods should make sense for all concrete states because you don’t want some of your states to have useless methods that will never be called.

3. Concrete States provide their own implementations for the state-specific methods.

   - To avoid duplication of similar code across multiple states, you may provide intermediate abstract classes that encapsulate some common behavior.
   - State objects may store a backreference to the context object.
   - Through this reference, the state can fetch any required info from the context object, as well as initiate state transitions.

4. Both context and concrete states can set the next state of the context and perform the actual state transition by replacing the state object linked to the context.
