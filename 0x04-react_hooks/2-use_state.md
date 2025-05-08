# useState

The useState hook is one of the most fundamental and commonly used hooks in React. They allow functional components to manage state.

State is simply the information that can change over time as a result of user actions or other events.

useState hook is imported from _React_

```jsx
import {useState} from "react";
```

When we call the **useState** hook, it returns an array with two elements, the current state value and a function to update the state. We also pass the initial value of our state as the argument to the useState call.

```jsx
import {useState} from "react";
import "./App.css"


function App() {
  const [number, setNumber] = useState(0); //destructure the array returned by the UseState hook

  function handleAddNumber() {
    setNumber(number + 1)
  }

  return(
    <div>
      <p>{number}</p>
      <button onClick={handleAddNumber}>Increment Number</button>
    </div>
  )
}

export default App
```

## Using a function to calculate the initial state

Sometimes, the initial state may be expensive to calculate. In this case, you can pass a function to the **useState** hook, the function will only run once (on the first render).

**For instance:**

```jsx
import {useState} from "react";
import "./App.css"


function App() {
  const [number, setNumber] = useState(function () {
    console.log("A very expensive calculation to derive number");
    return 10;})

  function HandleIncrementNumber () {
    setNumber(number + 1)
  }

  return <div>
    <p>{number}</p>
    <button onClick={HandleIncrementNumber}>increment</button>
  </div>
}

export default App
```

## Updating state based on the previous state

For this we pass a callback function to the state update function which takes the previous state as a parameter and returns a new state based on the previous state.

To demonstrate this we can increment a number until it reaches 10 and then start over from 1 once it reaches 10

```jsx
import {useState} from "react";
import "./App.css"


function App() {
  const [number, setNumber] = useState(function () {
    console.log("A very expensive calculation to derive number");
    return 0;})

  function HandleIncrementNumber () {
    setNumber(function(PreviousNumber) {
      PreviousNumber++;

      if(PreviousNumber === 10) return 1;
      return PreviousNumber;
    })
  }

  return <div>
    <p>{number}</p>
    <button onClick={HandleIncrementNumber}>increment</button>
  </div>
}

export default App
```

## Handling state with objects

We can also work with objects in our state:

```jsx
import {useState} from "react";
import "./App.css"


function App() {

  const [user, setUser] = useState({name:"Levis", age:"23"});

  return(
    <div>
      <p>{user.name}</p>
      <p>{user.age}</p>
    </div>
  )
}

export default App
```

### updating an object state

When updating an object state, we use the **spread** operator as shown:

```jsx
import {useState} from "react";
import "./App.css"


function App() {
  const [user, setUser] = useState({name:"Levis", age:23})

  function HandleUpdateAge() {
    setUser({...user, age: user.age + 1})
  }

  return(
    <div>
      <p>{user.name}</p>
      <p>{user.age}</p>
      <button onClick={HandleUpdateAge}>increment age</button>
    </div>
  )
}

export default App
```

#### Why use {...user}

State updates in React replace the entire state object. If you do:

```jsx
setProfile({age: user.age + 1 });
```

You will end up losing all the other object properties. Using _{...user}_ ensures all properties remain while updating only one.

## Handling state with arrays

We could also handle state with arrays:

```jsx
import {useState} from "react";
import "./App.css"


function App() {
  const [tasks, setTasks] = useState(["task1", "task2", "task3"])

  function handleAddTask() {
    setTasks([...tasks, "another task"])
  }

  return(
    <div>
      {tasks.map(task => <p key={Math.random()}>{task}</p>)}

      <button onClick={handleAddTask}>add task</button>
    </div>
  )
}

export default App
```