<h1><u>CallBack</u> <u>Hell</u></h1>
<p>

<h3>The 2 problems with CallBacks :</h3>

1. <b><u>CallBack</u> <u>Hell</u></b>

- <b>Asynchronous operations in JavaScript can be achieved through callbacks</b>. Whenever there are multiple dependent Asynchronous operations it will result in a lot of <b>nested callbacks</b>. This will cause a <b>'pyramid of doom'</b> like structure.

- Callbacks are useful when we want to perfrom some extra functionality with our already existing function for example passing an error handling callback to our already created function, BUT when callbacks within themselves start taking in other functions as callbacks then that mess that you are left with is known as the Callback Hell leading to <b>unreadable code</b>, hence <b>unmaintanable code</b>.

<code>Example :-</code>

```javascript
const cart = ["shoes", "kurta", "pants"];

api.createOrder(cart, function () {
  api.proceedToPayment(function () {
    api.showOrder(function () {
      api.updateWallet()
    });
  });
});

```

- The above code structure is called pyramid of doom.

2. <b><u>Inversion</u> <u>Of</u> <u>Control</u></b>

- When we pass a function to other function as a callback we are giving the called function the control of whether to even call it or not or maybe call it in a wrong context. For example a success callback is called when an error occours inside a called function (maybe due to human error while writing the code  for called function), this type of giving up of control over our functions is known as inversion of control.

- <b>Lose control of the program</b>, which means we gave out our function control to some other function and we don't know whether the function will ever execute our function or not.

- When we <b>give the control of callbacks</b> being called to some other API, this may create a lot of issues. That API may be buggy,  may not call our callback and create order as in the above example, may call the payment callback twice etc.

</p>