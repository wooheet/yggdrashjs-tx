# Transaction

[index.js:]()

Creates a new transaction object.

**Parameters**

-   `data` **Buffer or Array or Object** a transaction can be initiailized with either a buffer containing the RLP serialized transaction or an array of buffers relating to each of the tx Properties, listed in order below in the exmple.Or lastly an Object containing the Properties of the transaction like in the Usage example.For Object and Arrays each of the elements can either be a Buffer, a hex-prefixed (0x) String , Number, or an object with a toBuffer method such as Bignum
    -   `data.chain` **Buffer** 
    -   `data.version` **Buffer** transaction branch version
    -   `data.type` **Buffer** transaction branch type
    -   `data.timeStamp` **Buffer** transaction timestamp
    -   `data.bodyHashHex` **Buffer** body hash
    -   `data.bodyLength` **Buffer** body length
    -   `data.v` **Buffer** EC signature parameter
    -   `data.r` **Buffer** EC signature parameter
    -   `data.s` **Buffer** EC recovery ID

**Properties**

-   `raw` **Buffer** The raw rlp encoded transaction

**Examples**

```javascript
var rawTx = {
  chain: 'fe7b7c93dd23f78e12ad42650595bc0f874c88f7',
  version: '0000000000000000',
  type: '0000000000000000',
  timeStamp: '000000005bada008',
  bodyHashHex: 'f2feb937f282f105a24e47a69fbd0d705be3771cce695247d391fa5b6f8a7608',
  bodyLength: '000000000000028a',
  v: '1c',
  r: '5e1d3a76fbf824220eafc8c79ad578ad2b67d01b0c2425eb1f1347e8f50882ab',
  s: '5bd428537f05f9830e93792f90ea6a3e2d1ee84952dd96edbae9f658f831ab13'
};
var tx = new Transaction(rawTx);
```

## getSenderAddress

[index.js:](https://github.com/ethereumjs/ethereumjs-tx/blob/07b7b1a75168db1778d00fffd98324e8188036a1/index.js#L180-L187 "Source code on GitHub")

returns the sender's address

Returns **Buffer** 

## getSenderPublicKey

[index.js:](https://github.com/ethereumjs/ethereumjs-tx/blob/07b7b1a75168db1778d00fffd98324e8188036a1/index.js#L193-L198 "Source code on GitHub")

returns the public key of the sender

Returns **Buffer** 

## getUpfrontCost

[index.js:](https://github.com/ethereumjs/ethereumjs-tx/blob/07b7b1a75168db1778d00fffd98324e8188036a1/index.js#L266-L270 "Source code on GitHub")

the up front amount that an account must have for this transaction to be valid

Returns **BN** 

## hash

[index.js:](https://github.com/ethereumjs/ethereumjs-tx/blob/07b7b1a75168db1778d00fffd98324e8188036a1/index.js#L140-L166 "Source code on GitHub")

Computes a sha3-256 hash of the serialized tx

**Parameters**

-   `includeSignature` **[Boolean]** whether or not to inculde the signature (optional, default `true`)

Returns **Buffer** 

## sign

[index.js:](https://github.com/ethereumjs/ethereumjs-tx/blob/07b7b1a75168db1778d00fffd98324e8188036a1/index.js#L228-L235 "Source code on GitHub")

sign a transaction with a given a private key

**Parameters**

-   `privateKey` **Buffer** 

## toCreationAddress

[index.js:](https://github.com/ethereumjs/ethereumjs-tx/blob/07b7b1a75168db1778d00fffd98324e8188036a1/index.js#L131-L133 "Source code on GitHub")

If the tx's `to` is to the creation address

Returns **Boolean** 

## validate

[index.js:](https://github.com/ethereumjs/ethereumjs-tx/blob/07b7b1a75168db1778d00fffd98324e8188036a1/index.js#L277-L292 "Source code on GitHub")

validates the signature and checks to see if it has enough gas

**Parameters**

-   `stringError` **[Boolean]** whether to return a string with a dscription of why the validation failed or return a Bloolean (optional, default `false`)

Returns **Boolean or String** 

## verifySignature

[index.js:](https://github.com/ethereumjs/ethereumjs-tx/blob/07b7b1a75168db1778d00fffd98324e8188036a1/index.js#L204-L222 "Source code on GitHub")

Determines if the signature is valid

Returns **Boolean** 

## from

[index.js:](https://github.com/ethereumjs/ethereumjs-tx/blob/07b7b1a75168db1778d00fffd98324e8188036a1/index.js#L111-L115 "Source code on GitHub")

**Properties**

-   `from` **Buffer** (read only) sender address of this transaction, mathematically derived from other parameters.

## serialize

[index.js:](https://github.com/ethereumjs/ethereumjs-tx/blob/07b7b1a75168db1778d00fffd98324e8188036a1/index.js#L104-L104 "Source code on GitHub")

Returns the rlp encoding of the transaction

Returns **Buffer** 
