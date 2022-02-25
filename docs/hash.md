# Hash Functions

## SHA256
```javascript
const { Hash } = require('bsv-js');
let content = Buffer.from('Hash this string');
let hash = Hash.sha256(content);
console.log(hash.toString('hex')); // '1cac63f39fd68d8c531f27b807610fb3d50f0fc3f186995767fb6316e7200a3e'

let hash2x = Hash.sha256Sha256(content);
console.log(hash2x.toString('hex')); // '32ffb86000e9b881b23c4bc432f0ea36aa18cd2d756108cb8fc73794e606002d'
```
