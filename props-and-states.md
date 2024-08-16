What are props in a React component ?

Props are *immutable objects* passed to a component to render dynamic values inside the component.

```javascript
function UserInfo(props) {
  // object destructuring of props
  // to extract name and age out of it
  //
  // props value is:
  // {
  //   name: 'Name of person',
  //   age: 0,
  // }
  const { name, age } = props;

  return (
    <div className="pers">
      <h2>Name: {name}</h2>
      <h2>Age: {age}</h2>
    </div>
  );
}

export default UserInfo;

```

What is a state in a React component ?

```javascript
import { useState } from "react";

function PersonalInfo(props) {
  // object destructuring of props
  // to extract name and age out of it
  //
  // props value is:
  // {
  //   name: 'Name of person',
  //   age: 0,
  // }
  const { name, age } = props;

  // Using useState() hook
  // useState() returns:
  //    [initialState, stateSetterFunction]
  const [count, setCount] = useState(0);

  function onButtonClicked() {
    setCount(count + 1);
  }

  return (
    <div className="pers">
      <h2>Name: {name}</h2>
      <h2>Age: {age}</h2>

      <button onClick={onButtonClicked}>{count} times Clicked</button>
    </div>
  );
}

export default PersonalInfo;

```
