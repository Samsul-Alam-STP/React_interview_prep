# React Interview Questions and Answers

## Question 1: What is React?

### Answer:
React is a popular JavaScript library used for building user interfaces. It was developed by Facebook and is maintained by both Facebook and a community of individual developers. React allows developers to create reusable UI components and efficiently update and render those components when the underlying data changes.

React follows a component-based architecture, where the UI is broken down into small, self-contained pieces called components. Each component manages its own state and can be composed together to build complex user interfaces. React uses a virtual DOM (Document Object Model) for efficient updates and reconciliation with the actual DOM.

Example:
Here's a simple example of a React component:

```jsx
import React from 'react';

class HelloWorld extends React.Component {
  render() {
    return (
      <div>
        <h1>Hello, World!</h1>
      </div>
    );
  }
}
```

In this example, we define a `HelloWorld` component that renders a `<div>` containing an `<h1>` element with the text "Hello, World!". This component can be rendered and displayed in the UI using other React components or the ReactDOM library.

## Question 2: What is the difference between library and framework? Why react is known as a library rather than a framework? 

### Answer: 
The terms "library" and "framework" are often used interchangeably, but they have distinct differences in terms of their functionality and usage.

**Library:**
- A library is a collection of pre-written code that provides specific functionality or features. It is designed to be reused by developers to simplify and speed up their development process.
- Libraries typically consist of a set of functions, classes, or modules that can be imported and used in a project.
- Libraries do not impose a specific structure or workflow on the developer and usually focus on solving a particular problem or providing a specific set of tools.
- Developers have more control over the flow of their application when using libraries, as they can choose which parts to use and integrate into their codebase.
- Examples of libraries include NumPy (for numerical computations in Python), jQuery (for DOM manipulation in JavaScript), and requests (for making HTTP requests in various programming languages).

**Framework:**
- A framework is a more comprehensive software platform that provides a foundation for building applications. It defines the structure, flow, and behavior of an application and offers a set of tools and libraries to simplify development.
- Frameworks often include a specific architecture or design pattern, along with predefined rules and conventions that developers must follow.
- Unlike libraries, frameworks are more opinionated and provide a holistic approach to application development.
- Developers build their applications within the framework's structure, leveraging the provided features and components.
- Examples of frameworks include Django (for web development in Python), Ruby on Rails (for web development in Ruby), and Angular (for building web applications in TypeScript).

**Now, let's address why React is often referred to as a library rather than a framework:**

**React:**
- React is a JavaScript library developed by Facebook for building user interfaces.
- React focuses on the view layer of an application, providing a declarative way to create reusable UI components.
- It allows developers to build complex user interfaces by composing smaller, reusable components.
- React itself does not provide a complete solution for building an entire application. It is often used in combination with other libraries or frameworks, such as React Router for routing or Redux for state management.
- React's flexibility and modular nature make it more suitable to be categorized as a library rather than a complete framework.

Although React provides some framework-like features, such as its component architecture and virtual DOM, it lacks some defining characteristics of a full-fledged framework. React does not enforce a specific application structure, routing mechanism, or state management solution, leaving these choices to the developer.

Overall, the distinction between a library and a framework lies in their scope and level of control they offer to developers. Libraries provide specific functionality to be used at the developer's discretion, while frameworks offer a more comprehensive structure and impose a particular way of building applications. React's focus on the view layer and its modular nature align more closely with the characteristics of a library.

## Question 3: What are React components?

### Answer:
React components are the building blocks of a React application. They are reusable, self-contained pieces of code that manage their own state and define the UI structure and behavior. React components can be both functional and class-based.

**Functional Components:**
Functional components are JavaScript functions that return React elements. They are simpler and easier to understand compared to class components. Functional components are typically used for stateless or presentational components that don't have their own internal state or lifecycle methods.

Here's an example of a functional component:

```jsx
import React from 'react';

function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}
```

In this example, the `Greeting` component is a functional component that accepts a `name` prop and displays a greeting message using that prop.

**Class Components:**
Class components are ES6 classes that extend the `React.Component` base class. They are used for components that require state management, lifecycle methods, and more complex logic.

Here's an example of a class component:

```jsx
import React from 'react';

class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
  }

  incrementCount() {
    this.setState(prevState => ({ count: prevState.count + 1 }));
  }

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={() => this.incrementCount()}>Increment</button>
      </div>
    );
  }
}
```

In this example, the `Counter` component is a class component that maintains its own state (`count`) and renders a paragraph showing the current count value. The `incrementCount` method is used to update the state when the button is clicked.

## Question 4: What is JSX in React?

### Answer:
JSX (JavaScript XML) is an extension to JavaScript syntax that allows you to write HTML-like code within your JavaScript files when working with React. JSX is a syntactic sugar provided by React to define the structure and content of React components in a more declarative and intuitive manner.

JSX looks similar to HTML but it is not actually HTML. It gets transpiled into regular JavaScript function calls by tools like Babel before being executed in the browser. JSX allows you to include JavaScript expressions within curly braces `{}` to dynamically generate content.

Here's an example of JSX:

```jsx
import React from 'react';

function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}
```

In this example, the `<h1>` element with the text "Hello, {props.name}!" is written in JSX. The `props.name` expression is a JavaScript expression within curly braces, allowing us to dynamically insert the value of the `name` prop.

JSX makes it easier to understand and visualize the structure of your UI components. It also allows you to use the full power of JavaScript to handle dynamic content and logic within your components.

## Question 5: What is the difference between state and props in React?

### Answer:
In React, both state and props are used to manage and pass data to components, but they have different purposes and behaviors.

**State:**
State is a built-in feature of React components that represents the mutable data managed by a component. It is an object that holds information specific to that component and can be updated over time. State is typically used for data that can change, such as user input, component interactions, or fetched data.

To initialize the state, you use the `constructor` method within a class component or the `useState` hook in functional components. State should be modified using the `setState` method in class components or the `useState` hook in functional components, as direct assignment will not trigger re-rendering.

Here's an example of state usage in a class component:

```jsx
import React from 'react';

class Counter extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0
    };
  }

  incrementCount() {
    this.setState(prevState => ({ count: prevState.count + 1 }));
  }

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={() => this.incrementCount()}>Increment</button>
      </div>
    );
  }
}
```

In this example, the `Counter` component has a state property called `count`, which is initialized to 0. The `incrementCount` method updates the `count` state when the button is clicked, and the updated value is displayed in the UI.

**Props:**
Props (short for properties) are used to pass data from a parent component to a child component. They are read-only and should not be modified by the child component. Props are useful for providing configuration or dynamic data to a component, enabling the component to be reusable and customizable.

Props are passed to components in a similar way to HTML attributes. They can be any JavaScript value, including strings, numbers, objects, or even functions.

Here's an example of props usage:

```jsx
import React from 'react';

function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

function App() {
  return <Greeting name="John" />;
}
```

In this example, the `Greeting` component receives the `name` prop and displays a greeting message using that prop. The `App` component renders the `Greeting` component and provides the `name` prop with the value "John".

**To summarize, state is managed and updated internally by the component itself, while props are passed from parent components and remain unchanged by the receiving component. State is used for managing internal component data, whereas props are used for configuring and customizing child components.**

## Question 6: What are lifecycle methods in React?

### Answer:
Lifecycle methods are special methods provided by React that allow you to hook into different stages of a component's lifecycle. They provide an opportunity to perform certain actions at specific points in the component's existence, such as initialization, rendering, updating, and unmounting.

React components have three main phases in their lifecycle:

1. Mounting: This phase occurs when a component is being initialized and inserted into the DOM for the first time.

   - `constructor()`: The constructor method is called when a component is being created and allows you to initialize the component's state and bind event handlers.
   - `render()`: The render method is responsible for rendering the component's UI structure based on its props and state.
   - `componentDidMount()`: This method is invoked immediately after the component is mounted (i.e., inserted into the DOM). It is commonly used for initiating API calls, setting up subscriptions, or performing other initialization tasks that require access to the DOM.

2. Updating: This phase occurs when a component is being re-rendered due to changes in its props or state.

   - `render()`: The render method is called again to re-render the updated UI.
   - `componentDidUpdate(prevProps, prevState)`: This method is invoked immediately after an update occurs. It is often used to perform side effects based on prop or state changes. You should check if the changes in props or state are relevant before performing any actions to avoid infinite update loops.

3. Unmounting: This phase occurs when a component is being removed from the DOM.

   - `componentWillUnmount()`: This method is invoked just before the component is unmounted and destroyed. It is commonly used for cleaning up any resources, event listeners, or subscriptions created during the component's lifecycle.

Here's an example that demonstrates the usage of some lifecycle methods:

```jsx
import React from 'react';

class Timer extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      time: 0
    };
  }

  componentDidMount() {
    this.timerID = setInterval(() => {
      this.setState(prevState => ({ time: prevState.time + 1 }));
    }, 1000);
  }

  componentDidUpdate(prevProps, prevState) {
    if (prevState.time !== this.state.time) {
      console.log('Time updated:', this.state.time);
    }
  }

  componentWillUnmount() {
    clearInterval(this.timerID);
  }

  render() {
    return <p>Time: {this.state.time}</p>;
  }
}
```

In this example, the `Timer` component uses the `componentDidMount` method to start a timer when the component is mounted. The `componentDidUpdate` method is used to log the updated time value whenever it changes. The `componentWillUnmount` method is used to clear the timer before the component is unmounted.

**Note: React 17 introduced new lifecycle methods and deprecates some existing ones. If you're using React 16 or earlier, there are additional lifecycle methods like `componentWillMount` and `componentWillUpdate` that are still valid but have been deprecated in React 17 and later versions.**


## Question 7: What are React hooks?

### Answer:
React hooks are functions that allow you to use state and other React features in functional components. They were introduced in React 16.8 as a way to write stateful logic and reuse code in functional components without using class components.

The most commonly used hook is the `useState` hook, which allows you to add state to a functional component. It returns an array with two elements: the current state value and a function to update that state. Hooks must be called at the top level of the component, not inside loops, conditions, or nested functions.

Here's an example of using the `useState` hook:

```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  const incrementCount = () => {
    setCount(prevCount => prevCount + 1);
  };

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={incrementCount}>Increment</button>
    </div>
  );
}
```

In this example, the `useState` hook is used to add state to the `Counter` component. The `count` state is initialized with a value of 0, and the `setCount` function is used to update the state. The `incrementCount` function is a callback for the button's `onClick` event, which increments the `count` state when the button is clicked.

React hooks also provide other built-in hooks, such as `useEffect`, `useContext`, and `useReducer`, which allow you to manage side effects, access context, and handle more complex state management scenarios, respectively.

Hooks have significantly simplified the development process in React by enabling functional components to have local state and lifecycle behavior, reducing the need for class components in many cases.

## Question 8: What is the significance of the "key" prop in React?

### Answer:
The "key" prop is a special attribute in React that helps identify individual components in a list or iterable. It is used by React to efficiently update and reconcile the component tree when new elements are added, removed, or rearranged within a list.

When rendering a list of components, React needs a way to differentiate between them to know which components need to be updated. The "key" prop provides a unique identifier for each component within a list, allowing React to optimize the rendering process.

The "key" prop should be a stable and unique value within the list. It helps React determine if a component has changed, moved, or needs to be re-rendered. When a component's "key" changes, React will treat it as a new component and re-mount it, losing any existing state.

Here's an example that demonstrates the usage of the "key" prop in a list:

```jsx
import React from 'react';

function TodoList({ todos }) {
  return (
    <ul>
      {todos.map(todo => (
        <li key={todo.id}>{todo.text}</li>
      ))}
    </ul>
  );
}
```

In this example, the `TodoList` component receives an array of `todos` as a prop. When rendering the list, each `todo` item is assigned a "key" using the `todo.id` value. This ensures that each todo item has a unique identifier within the list.

It's important to note that the "key" prop should be specified directly on the component that is being iterated, such as the `<li>` element in this case. Assigning the "key" prop to a parent container or a wrapper component will not provide the desired optimizations.

By using the "key" prop correctly, React can efficiently update and reorder the list when new items are added or removed, resulting in improved performance and a better user experience.

## Question 9: What is the purpose of React context?

### Answer:
React context is a feature that allows data to be passed down through the component tree without the need for explicit props drilling. It provides a way to share data between components that are not directly connected through the parent-child relationship.

Context consists of two main components: the `Provider` and the `Consumer`. The `Provider` component is responsible for providing the data, while the `Consumer` component is used to consume that data anywhere within the component tree.

Here's an example that demonstrates the usage of React context:

```jsx
import React, { createContext, useContext } from 'react';

// Create a context
const ThemeContext = createContext();

// Parent component as the provider
function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Toolbar />
    </ThemeContext.Provider>
  );
}

// Child component consuming the context
function Toolbar() {
  const theme = useContext(ThemeContext);

  return (
    <div>
      <Button theme={theme} />
    </div>
  );
}

// Grandchild component using the context value
function Button({ theme }) {
  return <button className={theme}>Click me</button>;
}
```

In this example, the `ThemeContext` is created using the `createContext` function. The `App` component serves as the provider of the context, wrapping the `Toolbar` component with the `ThemeContext.Provider`. The `value` prop of the provider specifies the data to be shared, in this case, the theme value of "dark".

The `Toolbar` component consumes the context using the `useContext` hook, which allows it to access the theme value from the `ThemeContext`. The `Button` component, being a child of `Toolbar`, can also access the theme value without it being explicitly passed as a prop.

React context is particularly useful when there are multiple layers of components that need access to shared data or when passing data through intermediate components becomes cumbersome. It helps to keep the codebase clean and avoids prop drilling.

## Question 10: What is the purpose of React Router?

### Answer:
React Router is a popular routing library for React that enables the creation of single-page applications with multiple views. It provides a declarative way to handle client-side routing, allowing you to define different routes and their corresponding components.

The main purpose of React Router is to ensure that different components are rendered based on the current URL or route. It allows you to navigate between different views without reloading the entire page, providing a seamless and responsive user experience.

React Router provides several key components:

1. `BrowserRouter`: This component uses HTML5 history API to handle routing and synchronizes the UI with the current URL.

2. `Switch`: This component renders only the first matched route inside it, allowing exclusive rendering of routes.

3. `Route`: This component defines a route mapping between a URL path and a corresponding component to be rendered.

4. `Link`: This component creates a hyperlink to navigate between different routes.

Here's an example that demonstrates the basic usage of React Router:

```jsx
import React from 'react';
import { BrowserRouter, Switch, Route, Link } from 'react-router-dom';

function Home() {
  return <h1>Welcome to the Home page</h1>;
}

function About() {
  return <h1>About Us</h1>;
}

function App() {
  return (
    <BrowserRouter>
      <nav>
        <ul>
          <li>
            <Link to="/">Home</Link>
          </li>
          <li>
            <Link to="/about">About</Link>
          </li>
        </ul>
      </nav>

      <Switch>
        <Route exact path="/" component={Home} />
        <Route path="/about" component={About} />
      </Switch>
    </BrowserRouter>
  );
}
```

In this example, the `BrowserRouter` wraps the main `App` component, providing the routing functionality. The `Link` components are used to create navigation links to the respective routes. The `Switch` component ensures that only one route is rendered at a time. The `Route` components define the mapping between the URL path and the corresponding components to be rendered.

React Router simplifies the implementation of navigation and routing in React applications, allowing developers to create multi-page experiences within a single page. It provides a solid foundation for building complex applications with different views and routes.

## Question 11: What is React's virtual DOM and how does it work?

### Answer:
The virtual DOM is a concept in React that provides a virtual representation of the actual DOM (Document Object Model) structure. It is a lightweight copy of the real DOM and acts as a layer between the components and the actual browser DOM.

Here's how the virtual DOM works in React:

1. **Initial render:** When a React component is rendered, it creates a virtual DOM tree that mirrors the structure of the actual DOM. Each component and its properties are represented as a virtual node.

2. **Render diffing:** When the state or props of a component change, React re-renders the component and creates a new virtual DOM tree.

3. **Diffing algorithm:** React's reconciliation algorithm compares the new virtual DOM tree with the previous one to identify the differences or updates that need to be applied.

4. **Minimal updates:** Instead of directly manipulating the real DOM, React determines the minimal set of changes required to update the actual DOM based on the differences found during the diffing process.

5. **Batch updates:** React performs batch updates to minimize the number of DOM manipulations. It collects all the required changes and updates the real DOM in a single batch, which improves performance.

6. **Efficient updates:** React applies the identified changes to the real DOM, updating only the necessary elements. This approach is more efficient than directly manipulating the entire DOM structure.

By using the virtual DOM, React optimizes the rendering process and improves performance. Rather than updating the entire DOM tree when changes occur, React only updates the specific components or elements that have changed. This selective updating minimizes the number of operations needed, resulting in faster and more efficient rendering.

The virtual DOM also helps abstract away the complexity of working with the actual browser DOM. It provides a simpler programming model and allows developers to focus on building components and managing state, while React handles the efficient updating of the UI.

### Question 12: What is the role of the useEffect hook in React?

## Answer:
The `useEffect` hook in React allows you to perform side effects in functional components. Side effects can include things like fetching data from an API, subscribing to events, manipulating the DOM, or setting up timers.

The `useEffect` hook is called after the component has rendered and every time it re-renders due to changes in dependencies specified in the second argument of the hook. It takes two arguments: a callback function and an optional array of dependencies.

Here's an example to illustrate the usage of the `useEffect` hook:

```jsx
import React, { useState, useEffect } from 'react';

function ExampleComponent() {
  const [data, setData] = useState(null);

  useEffect(() => {
    // Perform side effect when component mounts
    fetchData();
    
    // Clean up the side effect when component unmounts
    return () => {
      cleanup();
    };
  }, []); // Empty dependency array means the effect runs only once

  useEffect(() => {
    // Perform side effect when 'data' changes
    if (data) {
      processAndDisplayData();
    }
  }, [data]);

  const fetchData = () => {
    // Code to fetch data from an API
    setData(fetchedData);
  };

  const cleanup = () => {
    // Code to clean up resources or subscriptions
  };

  const processAndDisplayData = () => {
    // Code to process and display the data
  };

  return (
    <div>
      {/* Component JSX */}
    </div>
  );
}
```

In this example, the `useEffect` hook is used to fetch data when the component mounts and also whenever the `data` state changes. The first `useEffect` call has an empty dependency array, `[]`, which means it will only run once, equivalent to `componentDidMount` in class components. The second `useEffect` call has `data` as a dependency, so it will run whenever `data` changes, similar to `componentDidUpdate` in class components.

The `useEffect` hook also supports a cleanup function, which is returned from the effect. This function is called when the component unmounts or when the effect is re-triggered. It is used to perform any necessary cleanup, such as canceling subscriptions or releasing resources.

By using the `useEffect` hook, you can incorporate side effects into your functional components, making them more powerful and flexible.

## Question 13: What is prop drilling in React and how can it be mitigated?

### Answer:
Prop drilling in React refers to the process of passing props down through multiple levels of nested components, even if some intermediary components do not require those props. This can lead to a verbose and cumbersome code structure where props are passed through components that don't use them directly, making the code harder to maintain and understand.

Prop drilling can be mitigated by using techniques such as context or component composition. Let's explore both options:

1. **Context:** React's context API allows you to create a context object that can be accessed by any component in the component tree without the need for explicit prop passing. It helps to share data between components that are not directly connected.

Here's an example of using context to mitigate prop drilling:

```jsx
import React, { createContext, useContext } from 'react';

// Create a context
const ThemeContext = createContext();

// Parent component
function App() {
  return (
    <ThemeContext.Provider value="dark">
      <ParentComponent />
    </ThemeContext.Provider>
  );
}

// Intermediate component
function ParentComponent() {
  return <ChildComponent />;
}

// Child component consuming context
function ChildComponent() {
  const theme = useContext(ThemeContext);

  return <div>{theme}</div>;
}
```

In this example, the `ThemeContext` is created using the `createContext` function. The `App` component serves as the provider of the context, wrapping the `ParentComponent` with the `ThemeContext.Provider` and providing the theme value as the context value. The `ChildComponent` consumes the context value using the `useContext` hook, accessing the theme without the need for prop drilling.

2. **Component composition:** Instead of passing props through intermediary components, you can use component composition to directly render components within other components. This approach allows you to compose complex components by combining smaller reusable components.

Here's an example of using component composition to mitigate prop drilling:

```jsx
import React from 'react';

// Parent component
function App() {
  const data = 'Hello, World!';
  return (
    <div>
      <ParentComponent data={data} />
    </div>
  );
}

// Intermediate component
function ParentComponent({ data }) {
  return <ChildComponent data={data} />;
}

// Child component
function ChildComponent({ data }) {
  return <div>{data}</div>;
}
```

In this example, the `App` component passes the `data` prop to the `ParentComponent`, which in turn passes it directly to the `ChildComponent`. By composing the components in this way, the prop drilling is avoided, and the `ChildComponent` receives the necessary data without intermediate components requiring the prop.

By using context or component composition, you can mitigate the need for excessive prop drilling and improve the maintainability and readability of your code.


## Question 14: What are controlled components in React?

### Answer:
In React, a controlled component is a form input element (such as `<input>`, `<textarea>`, or `<select>`) whose value is controlled by React's state. The state is used to maintain the current value of the input, and any changes to the input value are handled through React's event system.

Controlled components provide a way to synchronize the state of the input with the value displayed on the screen. This means that the input value is derived from the state, and any changes to the input value are reflected in the state, allowing React to be the single source of truth for the input's value.

Here's an example of a controlled component:

```jsx
import React, { useState } from 'react';

function InputExample() {
  const [value, setValue] = useState('');

  const handleChange = (event) => {
    setValue(event.target.value);
  };

  return (
    <input
      type="text"
      value={value}
      onChange={handleChange}
    />
  );
}
```

In this example, the `InputExample` component maintains the `value` state using the `useState` hook. The `<input>` element is rendered with the `value` prop set to the `value` state variable. The `onChange` event handler is assigned to the input, which updates the `value` state with the new input value whenever a change event occurs.

By controlling the value of the input through React's state, you can easily access and manipulate the input value, perform validation, or trigger other actions based on user input.

Controlled components provide a predictable and reliable way to manage form inputs in React, making it easier to implement features such as form validation, input masking, or complex input behaviors.

## Question 15: What is the difference between shallow rendering and full rendering in React testing?

### Answer:
In React testing, shallow rendering and full rendering are two different approaches to rendering and testing React components. They have different levels of depth and complexity in rendering the component and its child components.

1. **Shallow Rendering:**
Shallow rendering is a testing technique that renders only the component under test, without rendering its child components. Shallow rendering provides a fast and lightweight way to test the component in isolation, without worrying about the behavior or rendering of its child components.

Shallow rendering is often used to test the component's own logic, behavior, and rendering output. It allows you to assert on the component's state, props, and any lifecycle methods it may have. However, it doesn't provide insights into the behavior or rendering of child components, as they are not actually rendered during the shallow rendering process.

Shallow rendering is typically performed using testing utilities like Enzyme's `shallow` function or React Testing Library's `render` function.

2. **Full Rendering:**
Full rendering, also known as deep rendering or mount rendering, involves rendering the entire component tree, including all child components, as it would be rendered in a real application. Full rendering provides a more comprehensive and realistic testing environment, as it takes into account the interactions and behavior of the entire component hierarchy.

With full rendering, you can test the interactions and behavior between components, as well as verify the rendering output and behavior of child components. It allows you to test the component in a more integrated and realistic way, simulating real-world scenarios.

Full rendering is typically performed using testing utilities like Enzyme's `mount` function or React Testing Library's `render` function.

The choice between shallow rendering and full rendering depends on the specific testing needs and goals. Shallow rendering is often suitable for testing individual components in isolation, while full rendering is useful for testing the integrated behavior of components and their interactions with child components.

It's important to note that React Testing Library encourages testing from the user's perspective, focusing on the rendered output and user interactions rather than implementation details. It promotes testing components as users would interact with them, which aligns well with full rendering.

