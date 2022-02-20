# BSV

BSV-js is a general purpose library for building Bitcoin SV applications in
JavaScript. It was forked from [`moneybutton/bsv`](https://github.com/moneybutton/bsv)
in February 2022 with the following motivations:

- **Be a better steward of the library**. The BSV js library is mission-critical
for most BSV apps and services. I don't believe changes are required for the
sake of making changes, but maintainers must be engaged with developers who use
their software.
- **Keep this a pure JavaScript implementation**. [@Firaenix](https://github.com/Firaenix)
is doing sterling work with [`bsv-wasm`](https://github.com/Firaenix/bsv-wasm) -
which will blast this library out of the water performance wise. Instead I will
commit to keeping this a pure JavaScript library and focus on optimising bundle
size rather than performance.
- **Forward thinking**. I make no commitment to the legacy v1.x API, instead I
will maintain the v2.x master branch. Where justified I'll introduce new APIs such
as the recent [merkle proof standard](https://tsc.bitcoinassociation.net/standards/merkle-proof-standardised-format/)
and in some cases I'll remove code that isn't used commonly.

Some specific objectives on my TODO list:

- [ ] Improve documentation throughout and publish a dedicated documentation site.
- [ ] Implement the TSC [merkle proof standard](https://tsc.bitcoinassociation.net/standards/merkle-proof-standardised-format/).
- [ ] Replace the current `TxBuilder` module with an API based on [`txforge`](https://github.com/libitx/txforge).
- [ ] Replace the dependency on `bn.js` with native JavaScript BigInts.
- [ ] Replace the dependency on `bitcoin-elliptic` with a native JavaScript implementation of `secp256k1` (leveraging BigInts).
- [ ] Strip out any crypto dependencies that can be adequately replaced with
[SubtleCrypto](https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto)
APIs (and nodejs equivalents).
- [ ] Something to keep the TypeScript zealots happy.

---

Original readme:

bsv is a javascript library for Bitcoin SV (BSV) intended to satisfy certain
goals:

1. Support ease-of-use by being internally consistent. It should not be
   necessary to read the source code of a class or function to know how to use it.
   Once you know how to use part of the library, the other parts should feel
   natural.

2. Have 100% test coverage, or nearly so, so that the library is known to be
   reliable. This should include running standard test vectors from the reference
   implementation.

3. Library objects have an interface suitable for use with a command-line
   interface or other libraries and tools, in particular having toString,
   fromString, toJSON, fromJSON, toBuffer, fromBuffer, toHex, fromHex methods.

4. All standard features of the blockchain are implemented (or will be) and
   saved in lib/. All BIPs are correctly implemented and, where appropriate, saved
   as bip-xx.js in lib/ (since that is their standard name). In order to allow
   rapid development, Yours Bitcoin includes non-standard and experimental
   features. Any non-standard features (such as colored coins or stealth
   addresses) are labeled as such in index.js as well as in comments.

5. Expose everything, including dependencies. This makes it possible to develop
   apps that require fine-grained control over the basics, such as big numbers and
   points. However, it also means that you can hurt yourself if you misuse these
   primitives.

6. Use standard javascript conventions wherever possible so that other
   developers find the code easy to understand.

7. Minimize the use of dependencies so that all code can be easily audited.

8. All instance methods modify the state of the object and return the object,
   unless there is a good reason to do something different. To access the result
   of an instance method, you must access the object property(s) that it modifies.

9. Support web workers to unblock web wallet UIs when performing cryptography.

## Environment Variables

* `BSV_JS_BASE_URL` - Default "/".
* `BSV_JS_BUNDLE_FILE` - Default "bsv.js"
* `BSV_JS_WORKER_FILE` - Default "bsv-worker.js"
* `NETWORK` - Default "mainnet"

You can change the network to run the CLI in testnet mode:

```
NETWORK=testnet ./bin/bsv.js
```
