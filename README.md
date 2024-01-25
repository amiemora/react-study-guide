## What is React, and how does it differ from other JavaScript frameworks?
React is a JavaScript library for building user interfaces. It focuses on the component-based architecture, making UI development more manageable and modular.

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




















