### How to create a React Context?

To create a context in react, you need to import React , create the context with a value inside of it

Wrap it around a component or many components so they all can access the state later on.

```js
const ThemeContext = React.createContext('light');
```

```js
<ThemeContext.Provider value="dark">
  <MyComponent />
</ThemeContext.Provider>

```


```js
function MyComponent() {
  const theme = useContext(ThemeContext);
  return <div>The theme is: {theme}</div>;
}

```
