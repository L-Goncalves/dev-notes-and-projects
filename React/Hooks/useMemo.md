### UseMemo

useMemo is a React Hook that memorizes a value that is already computed, to avoid unnecessary recalculations everytime the component renders .

```js
const memoizedValue = useMemo(() => {
  // complex calculation
  return result;
}, [dependency]);
```

#### Common Use Cases:

* Heavy calculations (sorting or filtering large datasets)
* Derived State (When you derive values from props/state and want to avoid recalculating unless necessary)
* Avoid unnecessary re-renders (Useful when passing objects/arrays to child components using `React.memo`.)
* Memoizing expensive JSX
