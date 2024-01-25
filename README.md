## What is Rreact? 
- Open-source JS Library  
- Used for building User Interfaces   
- Simplifies SPA by using reusable components   

## What are the Key Features of React? 
1. **Virtual DOM**   
React utilizes a virtual representation of the DOM, allowing efficient updates minimizing direct manipulation of the actual DOM, resulting in improved performance. 


## Explain the concept of JSX and its advantages.
JSX stands for JavaScript XML - it allows us to write HTML inside our JS code. This JSX creates the Virtual DOM. 

## Differentiate between state and props in React.
State is an object that represents the internal data of a component. Props are properties passed to a component from its parent. Lifting state up involves moving the state to a common ancestor to share data between components. Default props are used to set default values for props.

## Performance Optimization:
The Virtual DOM is a lightweight copy of the actual DOM, allowing React to efficiently update the UI. Performance optimization includes using PureComponent, memoization with useMemo and useCallback, and optimizing renders with shouldComponentUpdate or React.memo.

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





















