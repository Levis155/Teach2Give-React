# Events

To add an event handler, you will first define a function and then pass it as a prop to the appropriate JSX tag.

For instance:

**Button.jsx file:**

```jsx
function Button() {
  function handleButtonClick() {
    alert("Button Clicked!");
  }

  return <button onClick={handleButtonClick}>click me</button>;
}

export default Button;
```

**App.jsx file:**

```jsx
import Button from "../components/button";

function App() {
  return (
    <>
      <Button />
    </>
  );
}

export default App;
```

## Inline Event Handlers

You can also define event handlers inline in the JSX as shown below:

```jsx
function Button() {
  return (
    <button
      onClick={() => {
        alert("You clicked me!");
      }}
    >
      click me
    </button>
  );
}

export default Button;
```

## Passing event handlers as props

You can pass event handlers as props as shown below:

**button.jsx:**

```jsx
function Button({ handleButtonClick }) {
  return <button onClick={handleButtonClick}>click me</button>;
}

export default Button;
```

**App.jsx**

```jsx
import Button from "../components/button";

function App() {
  return (
    <>
      <Button
        handleButtonClick={() => {
          alert("You clicked the button!");
        }}
      />
    </>
  );
}

export default App;
```
