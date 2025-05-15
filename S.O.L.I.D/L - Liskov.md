
### The L from S.O.L.I.D - Liskov Substitution Principle (LSP)

The L from S.O.L.I.D is from Liskov Substitution Principle. It states that a child class can do everything that a parent class can.

* Example of wrong code using the principle:

  ```js
  class Bird {
    fly() {
      console.log('I am flying');
    }
  }

  class Ostrich extends Bird {
    fly() {
      throw new Error('Ostrich cannot fly');
    }
  }

  function makeBirdFly(bird) {
    bird.fly();
  }

  const ostrich = new Ostrich();
  makeBirdFly(ostrich); // Error: Ostrich cannot fly

  ```
* Example of Good code using the principle:

```js
class Bird {
  fly() {
    console.log('I am flying');
  }
}

class Sparrow extends Bird {
  fly() {
    console.log('Sparrow is flying');
  }
}

// Function that works with any Bird
function makeBirdFly(bird) {
  bird.fly();
}

const sparrow = new Sparrow();
makeBirdFly(sparrow); // Works fine

```

Simply, ALL that a parent can do a child class should be able to do. (I thought this was the correct for every programming language btw)
