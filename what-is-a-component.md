In React, Components are building blocks of the user interface. They're self-contained, reusable piece of code that is a part of your React application.
React allows you to break down your app into smaller components, which makes it easier to manage and maintain your codebase.

### Types of component

- Class components(Stateful components) - Class components have their own state and can have lifecyle methods, because of this they're know as `stateful components`. Class components have a `render()` where you can write HTML markup for the component using JSX.

```javascript
// Class component example
import React, { Component } from "react";

class PersonalInfo extends React.Component {
  constructor() {
    super();
    this.state = {
      count: 0,
    }

    this.incrementValue = this.incrementValue.bind(this);
    this.decrementValue = this.decrementValue.bind(this);
  }

  incrementValue() {
    this.setState((prevState) => ({
      count: prevState.count + 1,
    }));
  }

  decrementValue() {
    this.setState((prevState) => ({
      count: prevState.count - 1,
    }));
  }


  render() {
    const { name, age } = this.props;
    const { count } = this.state;

    return (
      <div className="pers">
        <h2>Name: {name}</h2>
        <h2>Age: {age}</h2>

        <h2>{count}</h2>

        <button className="custom-button" onClick={this.incrementValue}>Increment</button>
        <button className="custom-button" onClick={this.decrementValue}>Decrement</button>
      </div>
    );
  }
}

export default PersonalInfo;

```
- Functional components(Stateless components) - Functional components are functions that accept props as the argument and returns JSX element. Functional components doesn't have their own state because of which they're known as `stateless components`, however, they can use `useState` hook which allows similar behavior as having state does.

```javascript
// Functional component example
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
