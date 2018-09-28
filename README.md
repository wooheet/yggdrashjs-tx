# SYNOPSIS 

# INSTALL
`npm install yggdrashjs-tx`

# USAGE

  - [example]()

```javascript
const YggdrashTx = require('yggdrashjs-tx')
const privateKey = Buffer.from('e331b6d69882b4cb4ea581d88e0b604039a3de5967688d3dcffdd2270c0fd109', 'hex')

const txParams = {
    "chain":'0xfe7b7c93dd23f78e12ad42650595bc0f874c88f7',
    "version":'0x0000000000000000',
    "type":'0x0000000000000000',
    "timeStamp":'0x000000005bada008',
    "bodyHashHex":'0xf2feb937f282f105a24e47a69fbd0d705be3771cce695247d391fa5b6f8a7608',
    "bodyLength":'0x000000000000028a'
}

const tx = new YggdrashTx(txParams)
const signature = tx.sign(privateKey)

const vrs = tx.vrs(signature);
const txHash = tx.getTxHash(signature)
```

# API
[./docs/](./docs/index.md)

# LICENSE
[MPL-2.0]()
