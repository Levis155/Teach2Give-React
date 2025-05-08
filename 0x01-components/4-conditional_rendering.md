# Conditional Rendering

React allows you to render different UI elements based on different conditions, this feature is called conditional rendering.


## Using _if_ statements

For instance to display welcome back when a user is not logged in and please log in if not

```jsx 
function Greet ({isLoggedIn}) {
  if(isLoggedIn === false) {
    return <h1>Please Log In</h1>
  } else {
    return <h1>Welcome Back!</h1>
  }
}

function App() {
  return (
    <>
      <Greet isLoggedIn = {true} />
    </>
  )
}

export default App
```

## Using the Ternary Operator

```jsx
function Greet ({isLoggedIn}) {
  return isLoggedIn ? <h1>Welcome Back!</h1> : <h1>Please Log In</h1>
}

function App() {
  return (
    <>
      < Greet isLoggedIn = {true} />
    </>
  )
}

export default App
```

## Logical AND Operator (&&)

Used when you want to render some jsx when a condition is true or render nothing otherwise.


```jsx
function Greet ({isLoggedIn}) {
  return isLoggedIn === true && <button>view account details</button>
}

function App () {
  return(
    <>
      <Greet isLoggedIn={false} />
    </>
  ) 
}

export default App
```