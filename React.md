## What is REACT ?
**React** is JavaScript Library for building userinterfacce.
Extremely popular, declarative, component-based, state-driven JavaScript library for building user interfaces created by facebook.

- **Declarative:** Telling react what a component should look like, based on current data/state.
- Rect is **abstraction** away from DOM: we never touch the DOM.
- **JSX:** a syntex that combines HTML, CSS, JavaScript as well as referencing other components.
- **State-driven:** REACT *reacts* to state changes by re-rendering the UI.

## Why React JS is popular compared to other JS frameworks like Angular?  
React has gained significant popularity compared to other JavaScript frameworks like Angular for several reasons:

1. **Component-Based Architecture**: React promotes a component-based architecture, allowing developers to build reusable UI components. This modularity makes it easier to manage and scale applications.

2. **Virtual DOM**: React uses a virtual DOM to optimize rendering. It updates only the parts of the DOM that have changed, leading to improved performance and a smoother user experience.

3. **Unidirectional Data Flow**: React follows a unidirectional data flow, making it easier to understand how data changes affect the UI. This predictability simplifies debugging and enhances maintainability.

4. **Rich Ecosystem**: React has a vast ecosystem of libraries and tools, such as React Router for routing and Redux for state management. This flexibility allows developers to choose the best tools for their specific needs.

5. **Strong Community Support**: React has a large and active community, providing extensive resources, tutorials, and third-party libraries. This support makes it easier for developers to find solutions and share knowledge.

6. **JSX Syntax**: React uses JSX, which allows developers to write HTML-like syntax within JavaScript. This integration makes it easier to visualize the UI structure and enhances developer productivity.

7. **Focus on UI**: React is primarily focused on building user interfaces, making it a great choice for projects where UI is a priority. This focus allows developers to create highly interactive and dynamic applications.

8. **Flexibility**: Unlike Angular, which is a full-fledged framework with a specific way of doing things, React is more flexible and can be integrated with other libraries or frameworks as needed.

9. **Performance**: React's efficient rendering and update mechanisms contribute to better performance, especially in applications with complex UIs.

10. **Adoption by Major Companies**: Many large companies, including Facebook (which developed React), Instagram, and Airbnb, use React, which boosts its credibility and encourages other developers to adopt it.

## What are the features of React JS ?
1. **JSX:** It serves as a syntax extension to JavaScript, facilitating the combination of HTML structures with JavaScript code within React files.
2. **Components:** A block of code that is dedicated to a smaller UI portion. Otherwords, we can divide a UI into multiple coding block so the we cand reuse it.
3. **Virtual DOM:** React employs a Virtual DOM, which is a lightweight representation of the actual DOM stored in memory. This approach allows React to selectively update only the relevant parts of the real DOM when the state of an object changes.
4. **Data Binding:** React adopts a one-way data-binding approach, ensuring a modular and efficient structure. Unidirectional data flew signifies that in a React app, child components are often nested within parent components.
5. **High Performance:** React's high performance is driven by its ability to update only the components that undergo changes, rather than refreshing the entire set. This results in significantly faster web applications.

## How to Components in React JS ?


## Describe the lifecycle of React component and how you would use it to fetch data ?

React provides lifecycle methods and hooks to handle logic at these phases.

### 1. **Mounting Phase**:
This phase happens when a component is created and added to the DOM for the first time.

- **`constructor()`**: (Class-based component) Called before the component is mounted. You can initialize state and bind event handlers here.
- **`render()`**: The method where the JSX is returned to be displayed in the DOM.
- **`componentDidMount()`**: (Class-based) Runs after the component is mounted. This is a great place to fetch data, set up subscriptions, or perform side effects.

### 2. **Updating Phase**:
This phase occurs when a component's state or props change, causing it to re-render.

- **`render()`**: The component re-renders when state or props change.
- **`componentDidUpdate(prevProps, prevState)`**: (Class-based) This method is invoked after the component is re-rendered due to state or props changes. You can perform side effects here, such as fetching new data based on the updated props or state.

### 3. **Unmounting Phase**:
This phase occurs when the component is removed from the DOM.

- **`componentWillUnmount()`**: (Class-based) This method is called just before the component is removed from the DOM. It is useful for cleaning up (e.g., canceling subscriptions, clearing timers).

### **Using Functional Components with Hooks**:
React Hooks introduced a simpler way to manage component lifecycle in **functional components**, especially the `useEffect` hook, which combines the capabilities of several lifecycle methods in class components.

- **`useEffect()`**: It can be used to handle side effects, including data fetching, and it runs after the component renders. It can replace `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.

---

### **Fetching Data Using Class-based Components**:

To fetch data in a class-based component, you typically use the `componentDidMount` lifecycle method. This ensures that the data is fetched after the component has been rendered into the DOM.

```javascript
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      data: null,
      loading: true,
    };
  }

  componentDidMount() {
    // Fetch data when the component is mounted
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => {
        this.setState({ data: data, loading: false });
      })
      .catch(error => console.error('Error fetching data:', error));
  }

  render() {
    const { data, loading } = this.state;
    return (
      <div>
        {loading ? <p>Loading...</p> : <div>{JSON.stringify(data)}</div>}
      </div>
    );
  }
}
```

### **Using Functional Components with `useEffect()`**:

In functional components, the `useEffect` hook is the equivalent of `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`. You can use it to fetch data when the component mounts.

```javascript
import React, { useState, useEffect } from 'react';

const MyComponent = () => {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    // Fetch data when the component mounts
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => {
        setData(data);
        setLoading(false);
      })
      .catch(error => console.error('Error fetching data:', error));
  }, []); // Empty dependency array ensures this effect runs only once (on mount)

  return (
    <div>
      {loading ? <p>Loading...</p> : <div>{JSON.stringify(data)}</div>}
    </div>
  );
};

export default MyComponent;
```

## Compare the useState and useReducer hooks in React.
- `useState` is suitable for simple state logic, providing a variable and function to update it. 
- `useReducer` is better for complex state logic that involvs multiple sub-values or when the next state depends on the previous one, as it lets you manage local state of complex components with a reducer function.
