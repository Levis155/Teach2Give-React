# Introduction

React is a JavaScript library for building user interfaces.

React was developed by Facebook in 20011 and was open-sourced in 2013, it is currently maintained by individual developers and other companies.

React is not a framework-it is not even exclusive to the web, it is used with other libraries to render to certain environments. For instance, react native can be used to build mobile applications.

To build for the web developers use React alongside ReactDOM.

React DOM is a separate package that enables React to update and render UI components on the web browser by directly interfacing with the browser's Document Object Model(DOM), ensuring smooth, dynamic user experiences.

## Why we need React

### Efficient UI Updates with Virtual DOM

React uses a Virtual DOM to efficiently update only the necessary pars when data changes, instead of reloading the entire page. This makes apps faster and more responsive.

### Component-Based Architecture

React promotes reusable components, reducing code duplication.

Components make large application easier to manage and scale.

### Declarative Syntax

React's JSX (JavaScript XML) makes UI code more readable and maintainable.

Instead of manually manipulating the DOM, you describe the UI state, and React ensures it updates accordingly.

### State Management

React makes handling dynamic data easier with its state and props system

## Setting up a React Project

There are two CLI tools for setting up a React project:

- create-react-app (deprecated)
- using vite

To set up a React project using vite, run:

```bash
npm init vite
```

or  

```bash
npm init vite@latest
```

This will walk you through a utility that will help you set up a React project.