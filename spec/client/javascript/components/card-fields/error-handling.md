# Error Handling

## Define error handler

```javascript
const onError = (err) => {
    console.error(err);
}
```

### Error codes

Read `err.code` and check for the following error types:

- `paypal.CardFields.ERROR.GENERIC_ERROR`: Catch-call error code
- __TODO__: Define specific error codes

## Single card field

### Vanilla Javascript

```javascript
paypal.CardFields({ onError })
    .render('#card-field-container');
```

### React

```javascript
const App = () => {
    return (
        <PayPalCardFields onError={ onError } />
    );
}
```

## Multiple card fields

### Vanilla Javascript

```javascript
const cardField = paypal.CardFields({ onError });

cardField.child(
    paypal.CardNumberField()
).render('#card-number-field-container');

cardField.child(
    paypal.CardCVVField()
).render('#card-cvv-field-container');

cardField.child(
    paypal.CardExpiryField()
).render('#card-expiry-field-container');
```

### React

```javascript
const App = () => {
    return (
        <PayPalCardFields onError={ onError }>
            <div id="card-number-field-container">
                <PayPalCardNumberField />
            </div>
            <div id="card-cvv-field-container">
                <PayPalCardCVVField />
            </div>
            <div id="card-expiry-field-container">
                <PayPalCardExpiryField />
            </div>
        </PayPalCardFields>
    );
}
```
