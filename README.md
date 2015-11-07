# Crowdstart Checkout

[![Join the chat at https://gitter.im/crowdstart/checkout](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/crowdstart/checkout?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
Our checkout widget makes it possible to start taking pre-orders in minutes,
and is quite customizable.

## Preview
![Screenshot Preview](examples/basic/basic_screenshot.png)

## Usage
Set the `href` of your button to `#checkout`.

```html
<a class="btn" href="#checkout">Buy Now</a>
```

Configure the checkout widget however you'd like.

```javascript
<script src="https://rawgit.com/crowdstart/checkout/master/checkout.js"></script>
<script>
  // Create a new client for Crowdstart API.
  var api = new Crowdstart.API('eyJhbGciOiJIUzUxMiIsInR5cCI6IkpXVCJ9.eyJiaXQiOjI0LCJqdGkiOiJVMDc0RlU3MHVhWSIsInN1YiI6IkVxVEdveHA1dTMifQ.g_MqPv2s0DnyFdhkUMzYn9mtKaXNwmlEM14WcFq_s5Yd2eqH16TB9thxOdDE8ylcoBMgyI3eimSHJxGq7oj-EA')

  // Create default order, should match whatever the user is trying to pre-order
  var order = new Crowdstart.Order('usd',[
    new Crowdstart.ItemRef('84cRXBYs9jX7w', -1),
    new Crowdstart.ItemRef('doge-shirt', 100)
  ]);

  // Create default user (pre-populated in form fields)
  var user = new Crowdstart.User('joe@fan.com', 'Joe', 'Fan')

  // Social sharing settings
  var config = {
    facebook:   'suchtees',
    googlePlus: 'suchtees',
    twitter:    'suchtees',
  }

  // Customize theme
  Crowdstart.setTheme({
    borderRadius: 5,
  })

  // Instantiate widget, can be called multiple times, overriding order in widget.
  Crowdstart.Checkout('checkout', api, order, user, config);
</script>
```

## Examples
You can find examples in [examples/](examples/basic/index.html). You can also
see it in action in the [Crowdstart
documentation](http://www.crowdstart.com/docs/checkout).

## Testing
To test locally, [phantomjs2](https://www.npmjs.com/package/phantomjs2) must be installed.
