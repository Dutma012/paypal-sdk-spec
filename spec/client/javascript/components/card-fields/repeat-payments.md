# Repeat Payments

## Basic Repeat Payments

___TODO__: Link to button doc for returning users

## Repeat payments with CVV

Collect the CVV field and make a repeat purchase using an existing tokenized card

### Payment method token

```javascript
const paymentMethodToken = 'xyz';
```

### Button

#### Vanilla Javascript

```javascript
const cardField = paypal.CardFields({
    paymentMethodToken,
    createOrder,
    onApprove
});

cardField.child(
    paypal.CardCVVField()
).render('#card-cvv-field-container')

cardField.child(
    paypal.Buttons()
).render('#card-submit-button-container')

cardField.render('#card-field-container');
```

#### React

```javascript
const App = () => {
    return (
        <PayPalCardFields
            paymentMethodToken={ paymentMethodToken }
            createOrder={ createOrder }
            onApprove={ onApprove }>

            <div id="paypal-card-cvv-field-container">
                <PayPalCardCVVField />
            </div>

            <paypal.Buttons />
        </PayPalCardFields>
    );
}
```

### Manual Submit

#### Vanilla Javascript

```javascript
const cardField = paypal.CardFields({
    paymentMethodToken,
    createOrder,
    onApprove
});

cardField.render('#card-field-container');

document.querySelector('#card-submit-button')
    ?.addEventListener('click', cardField.submit);
```

#### React

```javascript
const App = () => {
    const cardFieldRef = useRef();
    
    const submitCard = () => {
        cardFieldRef.current.submit();
    };

    return (
        <PayPalCardFields
            ref={ cardFieldRef }
            paymentMethodToken={ paymentMethodToken }
            createOrder={ createOrder }
            onApprove={ onApprove }>

            <div id="paypal-card-cvv-field-container">
                <PayPalCardCVVField />
            </div>

            <button onClick={ submitCard }>
                Submit
            </button>
        </PayPalCardFields>
    );
}
```