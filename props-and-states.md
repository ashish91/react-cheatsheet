What are props in a React component ?

Props are *immutable objects* passed to a child component from a parent component. For eg. props can be used to pass user session info to various components that needs it like user name, user email etc.

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

State are *mutable objects* that hold information about the component. States cannot be passed to another component. For eg. in an increment counter, the count is persisted in the state of the component.

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
