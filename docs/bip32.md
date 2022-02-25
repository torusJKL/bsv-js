# Bip32

## xprv

The extended private key (xprv) is used to derive an unbounded amount of addresses.

### from Random
```javascript
const { Bip32 } = require('bsv-js');
let bip32 = Bip32.fromRandom();
console.log(bip32.toString(); // prints the xprv
```

### from Seed
We can use a Bip39 mnemonic prhase and use it as the seed for the HD wallet (see Bip39 documentation).

```javascript
const { Bip32 } = require('bsv-js');
let bip32 = Bip32.fromSeed(seed); // seed needs to be created using Bip39
```

### export and import
The xprv can be stored as a string.

```javascript
const { Bip32 } = require('bsv-js');
let bip32 = Bip32.fromRandom();
let xprv = bip32.toString();

let bip32Import = Bip32.fromString(xprv);
```

### derived

The derivation path for Bip32 is usually in te following format: `m / account' / external / index`.
Since the introduction of Bip44 some wallets use the new format: `m / purpose' / coin_type' / account' / change / index`.

```javascript
const { Bip32 } = require('bsv-js');
let bip32 = Bip32.fromRandom();
let bip32Derived = bip32.derive(`m/0'/0/0`);
let address = Address.fromPubKey(bip32Derived.pubKey).toString();
```

### Testnet
```javascript
const { Bip32 } = require('bsv-js');
let bip32 = Bip32.Testnet.fromRandom()
console.log(bip32.toString()); // prints the tprv
console.log(bip32.toPublic().toString()); // prints the tpub
```

## xpub
```javascript
const { Bip32 } = require('bsv-js');
let bip32 = Bip32.fromRandom();
let bip32Public = bip32..toPublic();
console.log(bip32Public.toString()); // prints the xbup
```
