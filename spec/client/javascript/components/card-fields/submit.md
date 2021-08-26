# Submit card fields

## Button

### Vanilla Javascript

```javascript
const cardField = paypal.CardFields();

cardField.child(
    paypal.Buttons()
).render('#card-submit-button-container')

cardField.render('#card-field-container');
```

### React

```javascript
const App = () => {
    return (
        <PayPalCardFields>
            <paypal.Buttons />
        </PayPalCardFields>
    );
}
```

## Manual Submit

### Vanilla Javascript

```javascript
const cardField = paypal.CardFields();
cardField.render('#card-field-container');

document.querySelector('#card-submit-button')
    ?.addEventListener('click', cardField.submit);
```

### React

```javascript
const App = () => {
    const cardFieldRef = useRef();
    
    const submitCard = () => {
        cardFieldRef.current.submit();
    };

    return (
        <PayPalCardFields ref={ cardFieldRef }>
            <button onClick={ submitCard }>
                Submit
            </button>
        </PayPalCardFields>
    );
}
```