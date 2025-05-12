### UseContext

useContext is a React hook that lets you read values from a context without manually passing props through every component ("without prop drilling")

```js
const value = useContext(MyContext);
```

#### Common Use Cases:

When multiple components need access to the  **same global state!**

* Theme (dark/light)
* Auth user
* Language/locale
* App settings
