<h1><u>Promises</u></h1>
<p>

- We use Promise to do asynchronous operations

- Promises are objects which are used to perform asynchronous operations.

- They are just like placeholders to store a future value that will be returned after some time.

- They contain two properties:<br> - PromiseState - PromiseResult.

<code>Example :-</code>

```javascript
const cart = ["shoes", "pants", "kurta"];

createOrder(cart, function (orderId) {
  proceedToPayment(orderId, function (paymentInfo) {
    showOrderSummary(paymentInfo, function () {
      updateWalletBalance();
    });
  });
});

const promise = createOrder(cart);

// { data: orderDeatils }

promise.then(function (orderId) {
  proceedToPayment(orderId);
});

createOrder(cart)
  .then((orderId) => proceedToPayment(orderId))
  .then((paymentInfo) => showOrderSummary(paymentInfo))
  .then((paymentInfo) => updateWalletBalance(paymentInfo));
```

- Promises are immutable so it can't be altered as a result it helps to get rid off inversion of control that would be occurred in case callback and by chaining of promises we can get out of the callback hell.

- In chaining of promises we should use return to get the promise result so that we don't miss anything from the chain.

<b>Features of Promises</b> :

- Promises can help us to write trust worthy code.

- They give us the result prompt in three states: <br> 1) Pending <br> 2) Fulfilled <br> 3) Rejected <br>

- We can attach function to promise object and retrieve its value unlike callbacks no need to pass the function.

- Nesting can be done in Promises and with the help of that we can return the values in each individual chain.

- Ensures that whatever needs to happen on completion of an async task gets only called once (no matter how many times a promise is resolved or rejected).

<code>Example :-</code>

```javascript
const GitHub_API = "https://api.github.com/users/anwesh08";

const user = fetch(GitHub_API);

console.log(user);
```

<b>Why promise is important</b> :

- Promise is important because it solves two main drawbacks i.e. callback hell and inversion of control.

- For inversion of control, promise returns in the form of an object and as soon as the value is returned then only the next function will be called using the .then method.

- For callback hell, the promise use to make chaining and resolve the horizontal proceedings of code and proceed it with vertical flow.
  Here we have to use return if we are having chaining so that all the data will be return without any bugs.

- And another benefit of promises is that it is immutable.

</p>
