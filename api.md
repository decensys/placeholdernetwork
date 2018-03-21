API v0.1

I want to get latest block hash from explorer API

`GET https://exlporer.placeholder.network/api/v1/bitcoin/latestblockhash`

401 Unauthorized: You need a token

`GET https://exlporer.placeholder.network/api/v1/access/token`

401 Unauthorized: Who are you?

`GET https://exlporer.placeholder.network/api/v1/access/token -H publicKey`

402 Payment Required: Please provide signed transaction or receipt

`GET https://exlporer.placeholder.network/api/v1/access/token -H signed transaction, publicKey`

200 OK: `operationId`

`GET https://exlporer.placeholder.network/api/v1/jobs/operationId -H publicKey`

200 OK: Processing...


```contract OwnedIndex {

    mapping (bytes32 => string) ownedString;

    function set(string _str)
    {
        // Generates a key unique to sender and string
        ownedString[sha3(msg.sender, _str)] = str;
    }

    function clear(string _str)
    {
        // Must be the orignal sender to generate key to delete
        delete ownedString[sha3(msg.sender, _str)];
    }
}
```

Token created

`GET https://exlporer.placeholder.network/api/v1/jobs/operationId -H publicKey`

200 OK: `token` returned

`GET https://exlporer.placeholder.network/api/v1/bitcoin/latestblockhash -H publicKey, signed(token)`
