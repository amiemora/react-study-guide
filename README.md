## What is React? 
- Open-source JS Library.  
- Used for building User Interfaces.   
- Simplifies SPA by using reusable components.   

## What are the Key Features of React? 
1. **Virtual DOM**   
React utilizes a virtual representation of the DOM, allowing efficient updates minimizing direct manipulation of the actual DOM, resulting in improved performance.   
2. **Component Based Architecture**   
React structures user interfaces as modular, reusable components, promoting a more maintainable & scalable approach to building applications. 
3. **Reusability & Composition**
React enables the creation of reusable components that can be composed together, fostering a modular & efficient development process.   
4. **JSX**
JSX is a syntax extension for JS used in React, allowing developers to write HTML-like code within JS, enhancing readability & maintainability.   
5. **Declarative Syntax**   
Reace has a declarative programming style(JSX), where developers focus on "what" the UI should look like & React handles the "how" behind the scenes. This simplifies the code.  
6. **Community & Ecosystem**
React benefits from a vibrant & extensive community, contributing to a rich ecosystem of libraries, tools, & resources, fostering collaborative development & innovation.   
7. **React Hooks**   
Hooks are functions that enable functional components to manage state & lifecycle features, providing a more concise & expressive way to handle component logic. 

## What is DOM? 
- **Document Object Model** represents the web-page as a tree-like structure which allows JS to dynamically access & manipulate the content & structure of web-page.
- DOM is the actual representation of the web-page.
- Re-renders the entire page when updates occur.
- Can be slower, especially with frequent updates.
- Suitable for static websites & simple applications.

## What is Virtual DOM? 
- Specific to React only.
- Lightweight copy of the DOM.
- Reacts creates an exact copy of the DOM , this is the Virtual DOM.
- The user is interacting & makig changes to the Virtual DOM.
- If a user is changing any HTML element, Virtual DOM will only update that HTML element not the entire DOM.
- We only update changed elements, minimum re-renders. 
- React uses the Virtual DOM to effeciently update the UI without re-rendering the entire page, which helps improve performance & make the application more responsive.
- Re-renders only the changed parts efficiently.
- Optimized for faster rendering.
- Ideal for dynamic & complex SPA with frequent updates.

## What are React Components?
- A reusable building block for creating User Interfaces.

## What is a SPA? 
- A web-app that has only one single web-page.
- Whenever a user does some action on the website, the content is dynamically updated without refreshing or loading a new page.

## What are 5 advantages of React? 
1. Simple to build SPA (by using components).
2. React is cross-platform & open-source.
3. Lightweight & very fast (Virtual DOM).
4. Large Community & Ecosystem.
5. Testing is easy 

## What are the disadvantages of React?
- React is not a good choice for small applications.

## What is the role of JSX in React?
- Javascript XML.
- JSX is used by React to write HTML-like code.
- JSX is converted to JS via Babel because browsers understand JS not JSX.

## What is the difference between Declarative & Imperative syntax?
- Declarative syntax focuses on describing the desired result without without specifying the step-by-step process.
- JSX in React is used to write declarative syntax.
- Imperative Syntax involves step-by-step process to achieve a particular goal.
- JS has an imperative syntax. 

## What is Arrow Function Expression in JSX? 
```js
const Nav = (props) => {
return (
<div>
<h1>{props.name}</h1>
</div>
);
};
export default Nav;
```

## How does a React app load and display components?
- index.html loads first (single page).
- Then with the help of react-libraries the index.js file is loaded (JS entry point).
- Then app.js gets loaded (root component - placeholder for all child components).

## How does React provide reusability & composition?
- Through a component based architecture.
- Once you create a component you can reuse it.
- Composition is creating a bew & big component by combining existing small components.

## What are State, Stateless, Stateful & State Management? 
- State refers to the current data of the component.
- Stateful/State management means when a user performs some actions on the UI, then the React app. should be able to update & re-render that data or state on the UI.
- A stateless component, also known as a functional component, is a fundamental concept in React that represents a UI element without any internal state management.

## What are Props?
- Props (properties) are a way to pass data from a parent component to a child component. 

## What is NPM? What is the role of the node_modules folder?
- NPM (Node Package Manager) is used to manage the dependencies for your React project including the React library itself. 
- node_modules folder contains all the dependencies of the project including react libraries. 

## What is the role of a Fragment?
- A way ti group multiple children elements.
- Prevents the addition of unecessary nodes to the DOM.

## What is the spread operator?
- Used to expand & spread an array or object.

## What are forms of conditional rendering?
1. If/Else.
2. Ternary Operator. 
3. && Operator.
4. Switch Statement.

## Transpile VS Compile?
- Transpile :
   - transform
   - JSX --> JS
   - Babel
   - High-level language --> another High-level language 
- Compile : 
   - High-level language --> Lower-level language 

## What is prop drilling?
- The process of passing down props through multiple layers of components.

## 5 ways to avoid prop drilling
1. Use context API.
2. Use Redux.
3. Use component composition.
4. Use callback functions.
5. Use custom hooks.

## Functional VS Class Component? 
- Functional : 
    - Defined as JS Function.
    - Originally stateless but can now maintain state using hooks.
    - No life-cycle methods.
    - More readable & concise.
    - Does not use "this" keyword.
    - Does not use the "render ()" method.
- Class : 
    - Defined as a JS (ES6) class.
    - Can manage local state with "this.state".
    - Stateful components by using the life-cycle method.
    - Verbose (complex).
    - Uses the "render ()" method.

## What is Routing & Router in React? 
- Routing : Allows you to create a single-page web application with navigation without the need for a full-page refresh.
- React Router : A library for handling routing & enables navigation & rendering of different components based on the URL. 

## How to implement Routing in React? 
```js
npm install react-router-dom 
```
1. Install React Router.
2. Create Navigation.
3. Create Routes.

## What are the roles of <Routes> & <Route> in React Routing?
- The <Routes> component is used as the root container for declaring your collection of routes.
- The <Route> component is used to define a route & specify the component that should render when the route matches.
```js
<Routes>
   <Route path="/" element={<Home/>} />
   <Route path="/about" element={<About/>} />
   <Route path="/contact" element={<Contact/>} />
</Routes>
```



## Differentiate between state and props in React.
State is an object that represents the internal data of a component. Props are properties passed to a component from its parent. Lifting state up involves moving the state to a common ancestor to share data between components. Default props are used to set default values for props.


## useState 
Purpose: Manages state in functional components.     
```js
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

## useEffect
Purpose: Handles side effects in functional components (e.g., data fetching, subscriptions).
```js
import React, { useState, useEffect } from 'react';

function DataFetcher() {
  const [data, setData] = useState([]);

  useEffect(() => {
    // Fetch data from an API
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => setData(data))
      .catch(error => console.error('Error fetching data:', error));
  }, []); // Empty dependency array means it runs once on mount

  return (
    <ul>
      {data.map(item => (
        <li key={item.id}>{item.name}</li>
      ))}
    </ul>
  );
}
```

## useRef
Purpose: Creates a mutable object that persists across renders.  
```js
import React, { useRef, useEffect } from 'react';

function FocusInput() {
  const inputRef = useRef();

  useEffect(() => {
    // Focus on the input element when the component mounts
    inputRef.current.focus();
  }, []);

  return <input ref={inputRef} />;
}
```

## useContext
Purpose: Accesses the value of a React context.  
```js
import React, { createContext, useContext } from 'react';

// Create a context
const ThemeContext = createContext();

function ThemedComponent() {
  // Consume the context value
  const theme = useContext(ThemeContext);

  return <div style={{ background: theme.background, color: theme.text }}>Themed Content</div>;
}
```

## useReducer
Purpose: Manages more complex state logic using a reducer function.  
```js
import React, { useReducer } from 'react';

// Reducer function
const counterReducer = (state, action) => {
  switch (action.type) {
    case 'INCREMENT':
      return { count: state.count + 1 };
    case 'DECREMENT':
      return { count: state.count - 1 };
    default:
      return state;
  }
};

function Counter() {
  const [state, dispatch] = useReducer(counterReducer, { count: 0 });

  return (
    <div>
      <p>Count: {state.count}</p>
      <button onClick={() => dispatch({ type: 'INCREMENT' })}>Increment</button>
      <button onClick={() => dispatch({ type: 'DECREMENT' })}>Decrement</button>
    </div>
  );
}
```

## useCallback
Purpose: Memoizes a callback function to prevent unnecessary re-renders.
```js
import React, { useState, useCallback } from 'react';

function MemoizedComponent() {
  const [count, setCount] = useState(0);

  const increment = useCallback(() => {
    setCount(count + 1);
  }, [count]);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>Increment</button>
    </div>
  );
}
```

## useMemo
Purpose: Memoizes the result of a computation to optimize performance.
```js
import React, { useState, useMemo } from 'react';

function MemoizedComponent() {
  const [count, setCount] = useState(0);

  const squaredCount = useMemo(() => {
    return count * count;
  }, [count]);

  return (
    <div>
      <p>Count: {count}</p>
      <p>Squared Count: {squaredCount}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

## useImperativeHandle
Purpose: Customizes the instance value that is exposed when using React.forwardRef.
```js
import React, { useImperativeHandle, forwardRef, useRef } from 'react';

const MyComponent = forwardRef((props, ref) => {
  const inputRef = useRef();

  useImperativeHandle(ref, () => ({
    focusInput: () => {
      inputRef.current.focus();
    }
  }));

  return <input ref={inputRef} />;
});

// Usage
const myComponentRef = useRef();
myComponentRef.current.focusInput();
```

## useLayoutEffect
Purpose: Similar to useEffect, but fires synchronously after all DOM mutations. It's often used for tasks that require measurements or interactions with the DOM before the browser paints.
```js
import React, { useLayoutEffect, useState, useRef } from 'react';

function MeasureBox() {
  const [width, setWidth] = useState(0);
  const boxRef = useRef();

  useLayoutEffect(() => {
    // Measure the width of the box after it has been painted
    setWidth(boxRef.current.offsetWidth);
  }, []); // Empty dependency array ensures it runs once on mount

  return (
    <div>
      <div ref={boxRef} style={{ width: '200px', height: '200px', background: 'lightblue' }}>
        {/* Box content */}
      </div>
      <p>Box Width: {width}px</p>
    </div>
  );
}
```

## useDebugValue:
Purpose: Adds a label or custom formatting to custom hooks when using React DevTools. It helps developers understand the value of a custom hook in the DevTools.
```js
import React, { useState, useDebugValue } from 'react';

function useCustomHook(initialValue) {
  const [value, setValue] = useState(initialValue);

  // Provide a custom label for DevTools inspection
  useDebugValue(value > 10 ? 'High' : 'Low');

  return value;
}

function ComponentUsingCustomHook() {
  const result = useCustomHook(8);

  return <p>Value: {result}</p>;
}
```



















SOURCES: https://youtu.be/IMEzmmP3WAs?si=DJxLbzm7QlbkeJL7
