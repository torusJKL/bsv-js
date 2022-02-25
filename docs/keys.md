# Keys

## private key

### from random
```javascript
const { PrivKey } = require('bsv-js');
let privKey = PrivKey.fromRandom();
```

### from Wif
```javascript
const { PrivKey } = require('bsv-js');
let privKey = PrivKey.fromWif('KwR6KPt9r6GRaJp1AXxazP9rADxpzZReCR429nLdS9Ra8wRkXwZM');
```

### to Wif
The private key can be exported to the Wif format.
For Mainnet the private key always starts with either the letter 'K' or 'L'.
```javascript
const { PrivKey } = require('bsv-js');
let privKeyWif = PrivKey.fromRandom().toWif();
console.log(privKeyWif);
```

### to Testnet Wif
A private key can also be exported as a Tesnet Wif.
In this case the string will always start with a 'c'.
```javascript
const { PrivKey } = require('bsv-js');
PrivKey.Testnet.fromRandom().toWif()
```

## public key

### from privKey

```javascript
const { PrivKey, PubKey } = require('bsv-js');
let privKey = PrivKey.fromRandom();
let pubKey = PubKey.fromPrivKey(privKey);
```

## KeyPair

```javascript
const { PrivKey, PubKey, KeyPair } = require('bsv-js');
let privKey = PrivKey.fromRandom();
let pubKey = PubKey.fromPrivKey(privKey);
let keyPair = new KeyPair(privKey, pubKey);
```
