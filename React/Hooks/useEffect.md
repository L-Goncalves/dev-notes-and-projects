### useEffect

This hook is very simple to understand.

You're gonna be using this everyday when using react.

* It's good for: "doing something" when a depency changes. Think of this as ComponentDidMount and ComponentDidUpdate mixed.

Example:

```js
import React, { useState, useEffect } from 'react';

const UserList = () => {
  const [users, setUsers] = useState([]);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
  
    const fetchUsers = async () => {
      try {
        const response = await fetch('https://jsonplaceholder.typicode.com/users');
        const data = await response.json();
        setUsers(data);
        setLoading(false);
      } catch (error) {
        console.error('Failed to get Users:', error);
      }
    };

    fetchUsers();
  }, []); // Runs once when ComponentDidMount

  if (loading) return <p>Loading Users...</p>;

  return (
    <ul>
      {users.map((user) => (
        <li key={user.id}>{user.name} ({user.email})</li>
      ))}
    </ul>
  );
};

export default UserList;

```

```js
import React, { useState, useEffect } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);


  useEffect(() => {
    document.title = `Count: ${count}`;
    console.log('Updated Title!');
  }, [count]); // dependency: runs always when 'count' changes

  return (
    <div>
      <p>You've clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click here</button>
    </div>
  );
};

export default Counter ;

```

#### Good to know:

* **useEffect does not directly makes it re-render**, but runs once after the re-render, when component updates
