# Emit Task

Our offchain backend has a job queue builtin. The code for that queue framework can be found in the [rescue repository on Github](https://github.com/xh3b4sd/rescue). Our queue processes tasks every second. If the queue is empty, then nothing happens. But if there is a task in that queue, then the \`apiserver\` will process that task eventually. One of those tasks is created for every user who signs up on the Uvio platform. And for every new user we are minting UVX tokens, so that people can get started right away without having to worry about anything else.

We had a case where a user staked all of their testnet UVX tokens on one claim, not realizing that they couldn't use the platform anymore without UVX tokens. Because this was testnet, we minted more tokens for that user so that they could keep using the platform. Below is the task that we created as sorted set member in the task queue at \`rescue.io/api.uvio.network\`. The sorted set score should always be the task's object ID.

```json
{
  "core": {
    "task.rescue.io/cancel": "10",
    "task.rescue.io/object": "1728232152561715644"
  },
  "meta": {
    "user.uvio.network/object": "1728930724516057",
    "task.uvio.network/origin": "intern",
    "task.uvio.network/worker": "uvxminthandler"
  },
  "node": {
    "addr.rescue.io/method": "any"
  }
}
```

Once this task was created in the Redis sorted set, the \`apiserver\` processed it and printed the log below. Note that the \`apiserver\` could mint UVX tokens because it has the dedicated private key configured which has the \`BOT\_ROLE\` assigned, which is the smart contract role authorized to mint new tokens to addresses.

```json
{
  "time":"2024-10-06 16:32:31", 
  "leve":"debu", 
  "mess":"submitted UVX.mint transaction onchain", 
  "address":"0x20f564df9Aa13499c5033CA99DFF55112A31f8E5", 
  "amount":"100", 
  "signer":"0x52378bd0Fd701930F825a4Aa789ECEF0E4e57deF", 
  "transaction":"0x46c0c291802598275144a1ebee54b44fbaea932d2cc0975442b46bb195c1f062", 
  "call":"/opt/render/project/go/src/github.com/uvio-network/apiserver/pkg/contract/uvxcontract/uvx.go:129" 
}
```
