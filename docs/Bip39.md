# Bip39

Bip39 inrtoduced a mnemonic seed phrase from which a Bip32 HD wallet can be derived.

## Mnemonic

### 12 words
```javascript
const { Bip39 } = require('bsv-js');
let bip39 = Bip39.fromRandom();
console.log(bip39.toString(); // prints the 12 word mnemonic phrase
```

### 24 words
The default is 12 words (128 bits). For more words we can specify the entropy bits used as a multiple of 32 (minimum 128).

```javascript
const { Bip39 } = require('bsv-js');
let bip39 = Bip39.fromRandom(256);
console.log(bip39.toString(); // prints the 24 word mnemonic phrase
```

## seed
To use the mnemonic for a Bip32 HD wallet we need to export the mnemonic to a seed.

### standard

```javascript
const { Bip39 } = require('bsv-js');
let bip39 = Bip39.fromRandom();
let seed = bip39.toSeed();
```

### with passphrase
It is possible to add a passphrase in addition to the seed for additional security or to have multiple different wallets based on the same mnemonic phrase.

```javascript
const { Bip39 } = require('bsv-js');
let bip39 = Bip39.fromRandom();
let seed = bip39.toSeed('secret');
```
