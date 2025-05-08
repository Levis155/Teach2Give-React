# Rendering

Rendering in React refers to the process of converting React components into actual DOM elements that the browser can display.

React follows a **declarative approach** to rendering components, which means that developers specify what a component should look like, and React takes care of rendering the components to the screen.

This is in contrast to an **imperative approach** where developers would write code to manually manipulate the DOM to update the UI.

Virtual DOM is an important aspect of how React works.

It is a lightweight in-memory representation of the DOM and it is used to optimize the rendering of components in a React application.

When a component is rendered React creates a virtual DOM representation of the component. 

React compares the VDOM representation of the component with previous VDOM representation(if it exists). If there are differences between the two VDOMs, React calculates the minimum number of  DOM updates needed to bring the actual DOM into line with the new VDOM.

React then updates the actual DOM with the minimum number of DOM updates needed to reflect the changes in the VDOM.

This process is known as **reconciliation**, and it is an important aspect of how React works. 