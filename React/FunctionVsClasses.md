### Components vs Classes

Now, we're gonna take a look back how it works and what the different between those 2 are!

### Class Components

* They're all created using Javascript Classes Syntax (ex: ``class MyComponent extends React.Component``)
* They all need methods like render to return JSX and componentDidMount and ComponentDidUpdate
  ```js
  class MyComponent extends React.Component {
    constructor(props) {
      super(props);
      this.state = { count: 0 };
    }

    increment = () => {
      this.setState({ count: this.state.count + 1 });
    };

    render() {
      return (
        <div>
          <p>Count: {this.state.count}</p>
          <button onClick={this.increment}>Increment</button>
        </div>
      );
    }
  }

  ```

### Functional Components

They're more common in a day to day project, while classes you'll see on more older projects, the newer ones usually do use Functional Components

* They're javascript functions that return JSX, no need to use the "class".
* Before React 16.8, All functional components couldn't have a lifecycle or states, but with Hooks it all has changed!

Example:

```js
const MyComponent = () => {
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>Increment</button>
    </div>
  );
};

```
