# Address

The address can be created from the private and the public key.

```javascript
const { Address, PrivKey, PubKey } = require('bsv-js');
let privKey = PrivKey.fromRandom();
let pubKey = PubKey.fromPrivKey(privKey);

let address1 = Address.fromPrivKey(privKey).toString()
console.log(address1.toString());

let address2 = Address.fromPubKey(pubKey).toString()
console.log(address2.toString());
```
