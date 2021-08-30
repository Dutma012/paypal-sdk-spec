# Getting Started - PayPal JS SDK

Welcome to PayPal's JS SDK getting started guide. Learn how to accept payments on your website using card, PayPal, Venmo, and alternative payment methods.

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

## Sample Code

<!-- TODO: - link to each component spec docs, once complete (spec/client/javascript/components/) -->
