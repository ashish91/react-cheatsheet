## What is useState hook ?

useState hook is a hook that lets you add `state` variable to your component.

```javascript
const [state, setState] = useState(initialState)

// Usage of useState()
import { useState } from 'react';

function MyComponent() {
  const [age, setAge] = useState(28);
  const [name, setName] = useState('Taylor');

  // Lazy initialization of state
  const [todos, setTodos] = useState(() => createTodos());
  // ...
```

#### useState() returns an array of two values:

1. current value of the state.
2. setter function that updates the state value and triggers a re-render.


### What is lazy initialization of state ?

```javascript
  function initialCountState() {
    console.log('Expensive processing' + Date.now());
    // Expesive process like below:
    //    JSON.stringify(bigJSONObject);
    return 0;
  }

  const [count, setCount] = useState(() => initialCountState());
```
