# Base 58

Satoshi used a custom Base 58 encoding scheme for Bitcoin addresses that doesn't allow any confusing characters (no lower case L and no upper case i).
The encoding scheme can optionally include a hash checksum to make errors in copying an address almost impossible.

## Base58

Encoding without checksum.

### encode
```javascript
const { Base58 } = require('bsv-js');
let content = Buffer.from('Encode this string');
let base58 = Base58.encode(content);
console.log(base58.toString()); // '3t2eTa3VQWTTdRcSJpddxhtsx'
```

### decode
```javascript
const { Base58 } = require('bsv-js');
let decoded = Base58.decode('3t2eTa3VQWTTdRcSJpddxhtsx');
console.log(decoded.toString()); // 'Encode this string'
```

## Base58Check

Encoding with checksum.

### encode
```javascript
const { Base58Check } = require('bsv-js');
let content = Buffer.from('Encode this string');
let base58 = Base58Check.encode(content);
console.log(base58.toString()); // 'KqyYGBxyFFcC9EUQSK64KvpTY3gzmf'
```

### decode
```javascript
const { Base58Check } = require('bsv-js');
let decoded = Base58Check.decode('KqyYGBxyFFcC9EUQSK64KvpTY3gzmf');
console.log(decoded.toString()); // 'Encode this string'
```
