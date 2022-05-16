[Reference](https://docs.near.org/docs/api/rpc/block-chunk#chunk)

> Note: The NEAR docs don't include a sample response for `receipts`

    |-- receipt_id: string (nullable = true)
    |-- predecessor_id: string (nullable = true)
    |-- receiver_id: string (nullable = true)
    |-- actions: array (nullable = true)
    |    |-- element: struct (containsNull = true)
    |    |    |-- FunctionCall: struct (nullable = true)
    |    |    |    |-- args: string (nullable = true)
    |    |    |    |-- deposit: string (nullable = true)
    |    |    |    |-- gas: long (nullable = true)
    |    |    |    |-- method_name: string (nullable = true)
    |    |    |-- Transfer: struct (nullable = true)
    |    |    |    |-- deposit: string (nullable = true)