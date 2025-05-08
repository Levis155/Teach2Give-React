# Manipulating the DOM with Refs

React automatically updates the DOM to match your render output, so your components won't often need to manipulate it. However, sometimes you might need access to the DOM elements managed by React for example, to focus a node, scroll to it e.t.c. There is no built in way to do those things in React, so you will need a ref to the DOM node.

## Getting a reference to a node

To access a DOM node managed by React, first, import the useRef _Hook_

```jsx
import { useRef }from 'react';
```

Then use it to declare a ref inside your component:

```jsx
const myRef = useRef(null);
```

Finally pass your ref attribute to the jsx tag for which you want to get the DOM node:

```jsx
import { useRef } from "react";

function MyComponent () {
    const myRef = useRef(null)

    function handleClick() {
        myRef.current.classList.toggle('box');
    }

    return(
        <div>
            <div ref={myRef}></div>
            <button onClick={handleClick}>click</button>
        </div>
    )
}

export default MyComponent
```