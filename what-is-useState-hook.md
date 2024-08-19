## What is useState hook ?

`useState` is a React hook that lets you add `state` variable to your component. Stateless components use `useState` hook to persist state for them.

```javascript
// useState hook syntax
const [state, setState] = useState(initialState)
```
#### useState() accepts the initialState as an arg and returns an array of two values:

1. current value of the state.
2. setter function that updates the state value and triggers a re-render.

#### Here's an example using `useState()` hook:

```javascript

// Usage of useState()
import { useState } from 'react';

function MyComponent() {
  const [age, setAge] = useState(28);
  const [name, setName] = useState('Taylor');

  // Lazy initialization of state
  const [todos, setTodos] = useState(() => createTodos());
  // ...
```


### What is lazy intialState ?

The `initialState` passed to `useState` hook is used only in the initial render of the component and is disregarded in subsequent renders. If the initial state is a result of some expensive calculation then we can provide a function instead, which will executed only on initial render.

```javascript
  const [state, setState] = useState(() => {
    const initialState = someExpensiveComputation(props);
    return initialState;
  });
```
