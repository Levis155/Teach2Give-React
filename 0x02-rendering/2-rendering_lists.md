# Rendering Lists

When working with React, you will often times need to render lists of items.

## Displaying a List of Items In React

To achieve displaying a list of items in React, we are going to use JavaScript's built in _map_ method to iterate over our list of items; and map them from primitives or objects to HTML elements.

**Each element receives a mandatory key prop.**

When rendering lists in React, keys help React identify which items changed, which items were added, or removed.

**Applicants.jsx**

```jsx
function Applicants() {
  const applicants = ["Pascal", "Levis", "Gideon"];

  return (
    <div>
      {applicants.map((applicant) => (
        <p key={applicant}>{applicant}</p>
      ))}
    </div>
  );
}

export default Applicants;
```

**App.jsx**

```jsx
import Applicants from "../components/applicants";

function App() {
  return (
    <>
      <Applicants />
    </>
  );
}

export default App;
```

## Displaying a List of objects

It doesn't work any different for complex objects in JavaScript arrays. You iterate over the list with the map method again and output for each list item your HTML elements.

**applicants.jsx:**

```jsx
function Applicants() {
  const applicants = [
    { firstName: "Levis", lastName: "Mbui" },
    { firstName: "Pascal", lastName: "Juma" },
    { firstName: "Gideon", lastName: "Mwangi" },
  ];

  return (
    <div>
      {applicants.map((applicant) => {
        return (
          <p key={applicant.firstName}>
            {applicant.firstName} {applicant.lastName}
          </p>
        );
      })}
    </div>
  );
}

export default Applicants;
```

**App.jsx:**

```jsx
import Applicants from "../components/applicants";

function App() {
  return (
    <>
      <Applicants />
    </>
  );
}

export default App;
```
