# useEffect

The **useEffect** hook is a fundamental part of React that allows functional components to handle side effects.

A side effect in programming (especially in React) is anything a function does that affects something outside of itself.

These side effects include; fetching data from APIs, directly manipulation the DOM etc. 

useEffect hook is imported from React:

```jsx
import { useEffect } from 'react';
```

The useEffect hook takes in two arguments:

- The first argument is a function that is executed to handle the side effects.

- The second argument (optional) is an array of dependencies that determines when the effect runs.

## useEffect without any dependencies (runs on every render)

When _useEffect_ is used without any dependencies, it runs after every render:

```jsx
import {useState, useEffect} from "react";
import "./App.css"


function App() {
  const[number, setNumber] = useState(0);

  useEffect(() => {
    console.log(`component rendered ${number}`)
  })

  function handleIncrementNumber() {
    setNumber(number + 1)
  }


  return(
    <div>
      <p>{number}</p>
      <button onClick={handleIncrementNumber}>increment</button>
    </div>
  )
}

export default App
```

## useEffect with an empty dependency array(runs only once on mounting)

If you pass an empty dependency array ([]), useEffect runs only once.

```jsx
import {useState, useEffect} from "react";
import "./App.css"


function App() {
  const[number, setNumber] = useState(0);

  useEffect(() => {
    console.log(`component rendered ${number}`)
  }, [])

  function handleIncrementNumber() {
    setNumber(number + 1)
  }


  return(
    <div>
      <p>{number}</p>
      <button onClick={handleIncrementNumber}>increment</button>
    </div>
  )
}

export default App
```

**A use case for this would be fetching data when a component loads.**

## useEffect with dependencies (runs when dependencies change)

You can specify dependencies inside the array. The effect will only run if one of the dependencies changes.

```jsx
import {useState, useEffect} from "react";
import "./App.css"


function App() {
  const[number, setNumber] = useState(0);

  useEffect(() => {
    console.log(`component rendered ${number}`)
  }, [number])

  function handleIncrementNumber() {
    setNumber(number + 1)
  }


  return(
    <div>
      <p>{number}</p>
      <button onClick={handleIncrementNumber}>increment</button>
    </div>
  )
}

export default App
```