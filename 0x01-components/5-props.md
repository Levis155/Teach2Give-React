# Props 

Props(short for properties) are used to pass data from a parent component to a child component.

Props are passed into react components making these components highly reusable.

**Example:**

```jsx
function Greet (props) {
  return(
    <h1>Hello {props.firstName} {props.lastName}</h1>
  )
}

function App() {
  return(
    <>
        <Greet firstName = 'John' lastName = 'Doe' />
    </>

  )
}

export default App

```

## Props with destructuring

Instead of passing _props.firstName_ and _props.lastName_ we can destructure them as shown:

```jsx
function Greet({firstName, lastName}) {
  return(
    <h1>Hello {firstName} {lastName}!</h1>
  )
}

function App() {
  return(
    <>
        <Greet firstName = 'John' lastName = 'Doe' />
    </>

  )
}

export default App
```
## Props are read-only

Props cannot be modified inside the component

```jsx
function Greet({ firstName, lastName }) {
  firstName = "Emily"; // DON'T
  lastName = "Smith"; // DON'T
  return (
    <h1>
      Hello {firstName} {lastName}!
    </h1>
  );
}
```

## The children prop in React

In React, _children_ is a special prop that allows components to wrap and display other components, elements, or content inside them.

**We use the children property when a component doesn't know what it will hold**

```jsx
function Card({ children }) {
  return <div>{children}</div>;
}

function App() {
  return (
    <>
      <Card>
        <h2>Service 1</h2>
        <p>Lorem ipsum</p>
        <p>Dolor sit</p>
        <a href="#">Get Started</a>
      </Card>

      <Card>
        <h2>Service 2</h2>
        <p>Benefit 1</p>
        <p>Benefit 2</p>
        <a href="#">Get Started</a>
      </Card>
    </>
  );
}
```