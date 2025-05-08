# React Router Basics

Once you have _react-router-dom_ installed, there are three things you need to do to use it:

- setup your router
- Define your routes
- handle navigation

## Configuring the router

In this step all you need to do is import the specific router you need _(BrowserRouter for the web)_ and wrap your entire application in that router.

```jsx
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import App from "./App.jsx";
import { BrowserRouter } from "react-router-dom";
import "./index.css";

createRoot(document.getElementById("root")).render(
  <StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </StrictMode>,
);
```

## Defining Routes

The next step in React Router is to define you routes.

This is generally done at the top level of your application, such as in the App component, but can be done anywhere you want.

Defining routes is as simple as defining a single _Route_ component for each route in your application and then putting all those _Route_ components in a single _Routes_ component.

Whenever your URL changes, React Router will look at the routes defined in your _Routes_ component, and it will render the content in the _element_ prop of the _Route_ that has a path that matches the URL.

In the example below, if our URL was /books the the _BookList_ component would be rendered.

```jsx
import { Routes, Route } from "react-router-dom";
import Home from "./Home";
import BookList from "./BookList";

function App() {
  return (
    <>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/books" element={<BookList />} />
      </Routes>
    </>
  );
}

export default App;
```

A good thing about React Router is that when you navigate between pages, it will only refresh the content inside your Routes component. All the rest of the content on your page will stay the same which helps with performance and user experience.

## Handling Navigation

The final step to React Router is handling navigation. Normally in an application you would navigate with anchor tags, but React Router uses its own custom _Link_ component to handle navigation.

This _Link_ component is just a wrapper around an anchor tag that helps ensure all the routing and conditional re-rendering is handled properly so you can us it just like you would a normal anchor tag.

```jsx
import { Link } from "react-router-dom";

function Header() {
  return (
    <div>
      <Link to="/">Home</Link>
      <Link to="/books">Books</Link>
    </div>
  );
}

export default Header;
```

We can use the _NavLink_ component for navigation.

The _NavLink_ component works similar to _Link_ component, but it provides extra styling to indicate the active route in the navbar based on the active URL.

```jsx
import { NavLink } from "react-router-dom";

function Header() {
  return (
    <div>
      <NavLink
        className={({ isActive }) => (isActive ? "active-link link" : "link")}
        to="/"
      >
        Home
      </NavLink>
      <NavLink
        className={({ isActive }) => (isActive ? "active-link link" : "link")}
        to="/books"
      >
        Books
      </NavLink>
    </div>
  );
}

export default Header;
```