# useReducer

The _useReducer()_ hook in React is similar to _useState()_, but is intended for more complex state changes.

The _useReducer_ hook:

- Takes a _reducerFunction_ as its first argument. This _reducerFunction_ takes in the current state and an action object and returns a new state. It does not modify the original state, but rather returns a new state based on the action passed to it.

- Takes the initial state value as the second argument, mostly an object.

- Takes an (optional) initializer function that can be used to initialize state as the third argument.

- Returns an array containing the current state value and a _dispatch()
_ function that can be used to trigger state changes by dispatching actions to the reducer.

Below is a blueprint:

```jsx
import { useReducer } from "react";

function reducerFunction(state, action) {}
function App() {
  const [state, dispatch] = useReducer(reducerFunction, initialState);
  return <div></div>;
}

export default App;
```

```jsx
import { useReducer } from "react";

function reducerFunction(state, action) {
  if (action.type === "update-name") {
    return { ...state, name: "JOHNNY" };
  }

  if (action.type === "update-age") {
    return { ...state, age: state.age + 1 };
  }
}

function App() {
  const [profile, dispatch] = useReducer(reducerFunction, {
    name: "John",
    age: 25,
  });
  return (
    <div>
      <p>Name: {profile.name}</p>
      <p>Age: {profile.age}</p>
      <button onClick={() => dispatch({ type: "update-name" })}>
        Update Name
      </button>
      <button onClick={() => dispatch({ type: "update-age" })}>
        Update Age
      </button>
    </div>
  );
}
```

**NOTE: useReducer is not a replacement of the useState hook, we only use it when state management gets complex**