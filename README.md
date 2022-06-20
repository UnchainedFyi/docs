# Unchained
[Unchained](https://unchained.fyi) is the NEAR Protocol data lake. Perform complex data analysis on historical NEAR RPC data in real time using SQL.

As Unchained uses [Apache Spark](https://spark.apache.org/docs/latest/index.html) for data processing, [Spark SQL syntax](https://spark.apache.org/docs/latest/sql-ref-syntax-qry-select.html) is currently the only supported syntax.

Current Data is from the NEAR TestNet, see [NEAR explorer](https://explorer.testnet.near.org/).

## API
Retrieve NEAR RPC data by making authenticated requests to https://api.unchained.fyi/near/rpc/v1

## Sandbox
Log in and navigate to the [Unchained API Sandbox](https://app.unchained.fyi/sandbox) to perform ad-hoc or exploratory queries using our demo key. Enter your query in the text box, and hit submit. That's it!

Like what you see? [Apply for our Early Partner Program](https://forms.gle/AwFmZMBs3YMkaCFe9) for your own unthrottled API Key.

### Examples
#### cURL
Get the most recent 10 transactions:
```sh
curl --header "x-api-key: <your_key>" https://api.unchained.fyi/near/rpc/v1 \
  -X POST \
  -d '{"query":"select * from unchained.transactions limit 10"}'
```

Get Hash, Height, and Signature from blocks:
```sh
curl --header "x-api-key: <your_key>" https://api.unchained.fyi/near/rpc/v1 \
  -X POST \
  -d '{"select header.hash, header.height, header.signature from unchained.blocks limit 1"}'
```

Get all transactions associated with a public key:
```sh
curl --header "x-api-key: <your_key>" https://api.unchained.fyi/near/rpc/v1 \
  -X POST \
  -d '{"query": "select * from unchained.transactions where public_key like \"ed25519:39nKrVUHdrbSnfWVpJ1UmQ5KjZny5JqvUBm8bLkhmAc9\"}'
```

Get total number of transactions associated with a public key:
```sh
curl --header "x-api-key: <your_key>" https://api.unchained.fyi/near/rpc/v1 \
  -X POST \
  -d '{"query": "select count(*) from unchained.transactions where public_key like \"ed25519:39nKrVUHdrbSnfWVpJ1UmQ5KjZny5JqvUBm8bLkhmAc9\"}'
```

Get number of blocks finalized between timestamps (unix nanoseconds):
```sh
curl --header "x-api-key: <your_key>" https://api.unchained.fyi/near/rpc/v1 \
  -X POST \
  -d '{"query": "select count(*) from unchained.blocks where header.timestamp between 1650975390581513200 and 1651975390581513200"}'
```

Explode nested values in `receipts.actions`:
```sh
curl --header "x-api-key: <your_key>" https://api.unchained.fyi/near/rpc/v1 \
  -d '{"query":"select actions[1].transfer.deposit as deposit, actions[1].functionCall.method_name as method_name, actions[1].functionCall.gas as gas from unchained.receipts limit 3"}'
```

#### Python
Get the most recent 10 transactions
```python
# TODO
```
