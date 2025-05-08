# useRef

useRef hook allows you to create a mutable reference that persists across renders without causing a re-render when it updates.

Unlike _useState_, changing a _useRef_ value does NOT trigger a re-render.

It's often used for directly interacting with the DOM or storing values that need to persist between renders without affecting performance.

## Storing mutable values without re-renders

Call _useRef_ at the top level of your component and optionally pass the initial value.

_useRef_ returns an object with a single property **current** which is initially set to the initial value you have passed. This can later be set to something else.

```jsx
import {useRef} from "react";
import "./App.css"


function App() {
  console.log("component rendered")
const numberRef = useRef(20);

function handleIncrement() {
  numberRef.current += 1;
  console.log(numberRef);
}

return(
  <div>
    <button onClick={handleIncrement}>
      increment
    </button>
  </div>
)
}

export default App
```

## Storing a DOM reference

One of the most common uses of useRef is to get a reference to a DOM element. 

To do this initialize the _useRef_ hook and attach it to the DOM element using the ref prop.

```jsx
import { useRef } from "react";
import "./App.css";

function App() {
  const inputRef = useRef();

  function handleInputFocus() {
    inputRef.current.focus();
  }

  return (
    <div>
      <input type="text" placeholder="type your name" ref={inputRef} />

      <button onClick={handleInputFocus}>click</button>
    </div>
  );
}

export default App;

```