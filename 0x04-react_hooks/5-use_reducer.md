# useReducer

The _useReducer()_ hook in React is similar to _useState()_, but is intended for more complex state changes.

The _useReducer_ hook:

- Takes a _reducerFunction_ as its first argument. This _reducerFunction_ takes in the current state and an action object and returns a new state. It does not modify the original state, but rather returns a new state based on the action passed to it.

- Takes the initial state value as the second argument, mostly an object.

- Takes an (optional) initializer function that can be used to initialize state as the third argument.

- Returns an array containing the current state value and a _dispatch()
_ function that can be used to trigger state changes by dispatching actions to the reducer.