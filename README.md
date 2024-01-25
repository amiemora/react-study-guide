# React Study Guide 

### Basic Concepts:

#### What is React, and how does it differ from other JavaScript frameworks?
React is a JavaScript library for building user interfaces. It focuses on the component-based architecture, making UI development more manageable and modular.

**Explain the concept of JSX and its advantages.
JSX stands for JavaScript XML - it allows us to write HTML inside our JS code. This JSX creates the Virtual DOM. 

#### Differentiate between state and props in React.**
State is an object that represents the internal data of a component. Props are properties passed to a component from its parent. Lifting state up involves moving the state to a common ancestor to share data between components. Default props are used to set default values for props.

#### Performance Optimization:
The Virtual DOM is a lightweight copy of the actual DOM, allowing React to efficiently update the UI. Performance optimization includes using PureComponent, memoization with useMemo and useCallback, and optimizing renders with shouldComponentUpdate or React.memo.

### Hooks: 

useState 
Purpose: Manages state in functional components.
Example:

