### The S from S.O.L.I.D

The S from S.O.L.I.D is from Single Responsability principle. This affirms that a class or a module should only have a reason to be changed, this should be only responsible for one thing!


Explanation:

* Every class needs to have a single responsability. If the class starts to have multiple responsabilities, this can make a code hard to be changed and modified, because one changed can affect others.
* After applying the Single Responsability Principle, you guarrante that a change in any part of the system don't affect others that do not have direct correlation.


Example:

Lets suppose you have a class "Employee" that does two things:

* Calculate a salary
* Generate reports about the employee

This violates the SRP, because you have two responsabilities under 1 class!

*How to fix it?*

Create two separate classes:

1. Employee - that calculates just the salary
2. EmployeeReport - that is responsible for generating reports

This makes the code cleaner and after any change in the way of calculating the salary won't affect the other class.


Functional example of Violation of SRP:


```js
function processOrder(order) {
    // 1. Calculates total of order
    let total = order.itens.reduce((sum, item) => sum + item.price, 0);
  
    // 2. Generates report of the order
    console.log(`Report of order: ${order.id}, Total: ${total}`);
  
    // 3. Sends the order to payment
    processPayment(order);
}

```

Fix:

```js
function calculateTotal(order) {
    return order.itens.reduce((sum, item) => sum + item.preco, 0);
}

function generateReport(order, total) {
    console.log(`Generated Report of Order: ${order.id}, Total: ${total}`);
}

function processPayment(order) {
    // Logic for processing payments
}

function processOrder(order) {
    let total = calculateTotal(order);
    generateReport(order, total);
    processPayment(order);
}

```
