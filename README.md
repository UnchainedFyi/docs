# Unchained
[Unchained](app.unchained.fyi) is the NEAR Protocol data lake. Perform complex data analysis on historical NEAR RPC data in real time using SQL.

As Unchained uses [Apache Spark](https://spark.apache.org/docs/latest/index.html) for data processing, [Spark SQL syntax](https://spark.apache.org/docs/latest/sql-ref-syntax-qry-select.html) is currently the only supported syntax.

Current Data is from the NEAR TestNet, see [NEAR explorer](https://explorer.testnet.near.org/).

## API
Retrieve NEAR RPC data by making requests to https://api.unchained.fyi/v1/near/rpc

**[`jq`](https://stedolan.github.io/jq/download/) is a helpful command line tool for formatting json**

### Examples
#### cURL
Get the most recent 10 transactions:
```sh
curl https://api.unchained.fyi/v1/near/rpc -X POST \
  -H "Content-Type: application/json" \
  -d '{"query": "select * from transactions limit 10"}' \
  | jq
```

Get Hash, Height, and Signature from blocks:
```sh
curl -X POST -H "Content-Type: application/json" \
-d '{"query": "select header.hash, header.height, header.signature from blocks limit 1"}' \
https://api.unchained.fyi/v1/near/rpc \
| jq
```

Get all transactions associated with a public key:
```sh
curl -X POST https://api.unchained.fyi/v1/near/rpc \
-H "Content-Type: application/json" \
-d '{"query": "select * from transactions where public_key like \"ed25519:39nKrVUHdrbSnfWVpJ1UmQ5KjZny5JqvUBm8bLkhmAc9\""}' \
| jq
```

Get total number of transactions associated with a public key:
```sh
curl -X POST https://api.unchained.fyi/v1/near/rpc \
-H "Content-Type: application/json" \
-d '{"query": "select count(*) from transactions where public_key like \"ed25519:39nKrVUHdrbSnfWVpJ1UmQ5KjZny5JqvUBm8bLkhmAc9\""}' \
| jq
```

Get number of blocks finalized between timestamps (unix nanoseconds):
```sh
curl -X POST https://api.unchained.fyi/v1/near/rpc \
-H "Content-Type: application/json" \
-d '{"query": "select count(*) from blocks where header.timestamp between 1650975390581513200 and 1651975390581513200"}' \
| jq
```


#### Python
Get the most recent 10 transactions
```python
# TODO
```

## Sandbox
Log in and navigate to the [Unchained Sandbox](https://app.unchained.fyi/sandbox) to perform ad-hoc or exploratory queries. Enter your query in the text box, and hit submit. That's it!
