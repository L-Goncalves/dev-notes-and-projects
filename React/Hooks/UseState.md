### UseState

This hook is very simple to understand.

You're gonna be using this everyday when using react.

* It's good for: saving values and update those inside functional components

Example:


```js
const [count, setCount] = useState(0);

setContador(count+ 1);
```

#### Good to know:

* UseState triggers re-render of that component, everytime for example, ``setCount`` gets called it triggers a re-render of that component
