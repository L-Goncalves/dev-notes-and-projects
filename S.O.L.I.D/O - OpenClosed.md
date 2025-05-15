### The O from S.O.L.I.D

The O from S.O.L.I.D is from Open Closed principle. This affirms that a classes should be  open to addition / extension but closed for modification.

* Benefits:
  * Easy to add: New features can be added without altering existing code.
  * Bug Reduction: Minimizes the risks of adding new buts into core features
* Example of bad pratice: modify a class directly to add a new behaviour.

```js
class Logger {
  log(message, type) {
    if (type === 'info') {
      console.log(`INFO: ${message}`);
    } else if (type === 'error') {
      console.error(`ERROR: ${message}`);
    } else if (type === 'warn') {
      console.warn(`WARN: ${message}`);
    }
  }
}

```

If you want to support new log types (`debug`, `fatal`, etc.), you need to **modify** the `log` method. violating OCP.

* Good Example (follows Open/Closed using strategy pattern)

```
class Logger {
  constructor() {
    this.strategies = {};
  }

  addStrategy(type, fn) {
    this.strategies[type] = fn;
  }

  log(message, type) {
    const strategy = this.strategies[type];
    if (strategy) {
      strategy(message);
    } else {
      console.log(`DEFAULT: ${message}`);
    }
  }
}

// Define strategies
const infoLogger = (msg) => console.log(`INFO: ${msg}`);
const errorLogger = (msg) => console.error(`ERROR: ${msg}`);
const warnLogger = (msg) => console.warn(`WARN: ${msg}`);

// Usage
const logger = new Logger();
logger.addStrategy('info', infoLogger);
logger.addStrategy('error', errorLogger);
logger.addStrategy('warn', warnLogger);

// Now we can extend without modifying
logger.log('Server started', 'info');
logger.log('Something went wrong', 'error');
logger.log('This is a warning', 'warn');

// Adding new type without touching Logger class
logger.addStrategy('debug', (msg) => console.debug(`DEBUG: ${msg}`));
logger.log('Debugging app', 'debug');

```
