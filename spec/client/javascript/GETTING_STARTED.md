# Getting Started - PayPal JS SDK

Welcome to PayPal's JS SDK getting started guide. Learn how to accept payments on your website using card, PayPal, Venmo, and alternative payment methods.


## Loading the Client SDK

There are two ways you can load the client side SDK:

1. You can add it in a script tag on the page.

Style:
<script src="www.paypal.com?authToken=<asdf>">

- we've strayed frmo competition a bit as in we don't pass teh config later into a function or class



Notes:
- location of tag
- attributes on tag
- url params

2. You can install as a module from npm.

```js
import { loadScript } from "paypal";

const configuration = {};


try {
  await loadScript(configuration)
} catch(error) {
  console.error(error.code);
}
```
TODO: link to error spec


# Westin + Joe Notes:

Assumptions:
- we are focusing on the client only integration
- comparing braintree, paypal, stripe

Notes:
- Do we start with getting tokens or straight into haivng the token and writing js
- Do we need to do the manual token exchange or can we do it from the dashboard like Stripe?
-

## Creating a Sandbox

## Creating an Account
What does this mean:
* what pricing model is being setup
* what methods are they eligible for: Credit Card vs ACH
-  how can we make this clear as they are making their sandbox
* what teams need to be involved

## Getting a Token
Exchange clientid and secret get token:
* paypal does it with a curl
* braintree does it with auth header approach
* stripe just gives you the "publishable" key


# Original PR Below

## Add the SDK script

There are two ways you can integrate the SDK.

1. You can add it in a script tag. After the script is loaded, you can reference `window.paypal` to use the sdk. Replace YOUR_CLIENT_ID with your client ID.

```js
<script src="https://www.paypal.com/sdk/js?client-id=YOUR_CLIENT_ID"></script>
```

2. You can use it as a module. The @paypal/sdk library provides a loading wrapper for the JS SDK script so you can easily load it using JavaScript.

```js
import { loadScript } from "@paypal/sdk";
let paypal;
try {
  paypal = await loadScript({ clientID: YOUR_CLIENT_ID })
}
catch (err) {
  console.error("failed to load the PayPal JS SDK script", err);
}
```

## Sample Integration Code

<!-- TODO: - link to each component spec docs, once complete (spec/client/javascript/components/) -->


## Moving from Sandbox Production
### Steps:
1. prove you are real to us

