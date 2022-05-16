[Reference](https://docs.near.org/docs/api/rpc/block-chunk#chunk)

> Note: The NEAR docs don't include a sample response for `transactions`

    |-- hash: string (nullable = true)
    |-- nonce: long (nullable = true)
    |-- public_key: string (nullable = true)
    |-- receiver_id: string (nullable = true)
    |-- signature: string (nullable = true)
    |-- signer_id: string (nullable = true)
    |-- actions: array (nullable = true)
    |    |-- element: struct (containsNull = true)
    |    |    |-- FunctionCall: struct (nullable = true)
    |    |    |    |-- args: string (nullable = true)
    |    |    |    |-- deposit: string (nullable = true)
    |    |    |    |-- gas: long (nullable = true)
    |    |    |    |-- method_name: string (nullable = true)