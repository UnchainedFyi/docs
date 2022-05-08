# Unchained 
[Unchained](app.unchained.fyi) is the NEAR Protocol data lake. Perform complex data analysis on historical NEAR RPC data in real time using SQL.

As Unchained uses [Apache Spark](https://spark.apache.org/docs/latest/index.html) for data processing, [Spark SQL syntax](https://spark.apache.org/docs/latest/sql-ref-syntax-qry-select.html) is currently the only supported syntax.

## API
Retrieve NEAR RPC data by making requests to https://api.unchained.fyi/v1/near/rpc

### Examples
#### cURL
Get the most recent 10 transactions

```sh
curl https://api.unchained.fyi/v1/near/rpc -X POST \
  -H "Content-Type: application/json" \
  -d '{"query": "select * from transactions order by TODO limit 10"}'
```

#### Python
Get the most recent 10 transactions
```python
# TODO
```

## Sandbox
Log in and navigate to the [Unchained Sandbox](https://app.unchained.fyi/sandbox) to perform ad-hoc or exploratory queries. Enter your query in the text box, and hit submit. That's it!
