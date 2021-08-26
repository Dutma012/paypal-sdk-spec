# Render Card Fields

## Single card field

### Vanilla Javascript

```javascript
paypal.CardFields()
    .render('#card-field-container');
```

### React

```javascript
const App = () => {
    return (
        <PayPalCardFields />
    );
}
```

## Multiple card fields

### Vanilla Javascript

```javascript
const cardField = paypal.CardFields();

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
        <PayPalCardFields>
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

## Teardown

### Single card field

```javascript
const cardField = paypal.CardFields();
cardField.render('#card-field-container');

cardField.destroy();
```

### Multiple card fields

```javascript
const cardField = paypal.CardFields();

cardField.child(
    paypal.CardNumberField()
).render('#card-number-field-container');

cardField.child(
    paypal.CardCVVField()
).render('#card-cvv-field-container');

cardField.child(
    paypal.CardExpiryField()
).render('#card-expiry-field-container');

cardField.destroy();
```