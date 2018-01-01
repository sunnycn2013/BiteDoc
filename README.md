

[比特币相关资料](https://github.com/sunnycn2013/BiteDoc/blob/master/ziliao.md)

### 1.取得钱包相关信息

 ```

命令行请求：
curl --user bitbs123 --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getinfo", "params": [] }' -H 'content-type: text/plain;' http://119.28.16.55:23114/

请求参数：
{
    "jsonrpc": "1.0",
    "id": "curltest",
    "method": "getinfo",
    "params": [
        
    ]
}

"result": {
        "version": 140200,
        "protocolversion": 70015,
        "walletversion": 130000,
        "balance": 0.00000000,
        "blocks": 500628,
        "timeoffset": 0,
        "connections": 0,
        "proxy": "127.0.0.1:9050",
        "difficulty": 1873105475221.611,
        "testnet": false,
        "keypoololdest": 1513758957,
        "keypoolsize": 100,
        "paytxfee": 0.00000000,
        "relayfee": 0.00001000,
        "errors": ""
    },
    "error": null,
    "id": "curltest"
}

```


### 2.取得钱包余额

```
命令行请求：
curl --user bitbs123 --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "getbalance", "params": [] }' -H 'content-type: text/plain;' http://119.28.16.55:23114/

{
    "jsonrpc": "1.0",
    "id": "curltest",
    "method": "getbalance",
    "params": []
}

{"result":0.00000000,"error":null,"id":"curltest"}

```

### 3. 验证一个钱包地址是否有效

```
0x68656c6c6f20776f726c64  //钱包地址
命令行请求：
curl --user bitbs123 --data-binary '{"jsonrpc": "1.0","id": "curltest","method": "validateaddress","params": ["0x68656c6c6f20776f726c64"]}' -H 'content-type: text/plain;' http://119.28.16.55:23114/

{
    "jsonrpc": "1.0",
    "id": "curltest",
    "method": "validateaddress",
    "params": [
        "0x68656c6c6f20776f726c64"
    ]
}

{"result":{"isvalid":false},"error":null,"id":"curltest"}
```


### 4. 根据用户ID，生成交易地址

```
命令行请求：

curl --user bitbs123 --data-binary '{"jsonrpc": "1.0","id": "curltest","method": "getnewaddress","params": ["389878212@qq.com"]}' -H 'content-type: text/plain;' http://119.28.16.55:23114/

{
    "jsonrpc": "1.0",
    "id": "curltest",
    "method": "getnewaddress",
    "params": [
        "389878212@qq.com"
    ]
}

//返回比特币钱包地址
{"result":"1BAmBDQeqdw5C4J9iPz9x86RfuE8DdrvrZ","error":null,"id":"curltest"}
```


### 5. 根据用户ID，获取交易记录

```
命令行请求：

curl --user bitbs123 --data-binary '{"jsonrpc": "1.0","id": "curltest","method": "listtransactions","params": ["1BAmBDQeqdw5C4J9iPz9x86RfuE8DdrvrZ"]}' -H 'content-type: text/plain;' http://119.28.16.55:23114/

{
    "jsonrpc": "1.0",
    "id": "curltest",
    "method": "listtransactions",
    "params": [
        "1BAmBDQeqdw5C4J9iPz9x86RfuE8DdrvrZ"
    ]
}

{"result":[],"error":null,"id":"curltest"}
```


### 6. 查出所有收到的币以地址
```
命令行请求：
curl --user bitbs123 --data-binary '{"jsonrpc": "1.0","id": "curltest","method": "listreceivedbyaddress","params": []}' -H 'content-type: text/plain;' http://119.28.16.55:23114/

{
    "jsonrpc": "1.0",
    "id": "curltest",
    "method": "listreceivedbyaddress",
    "params": []
}

{"result":[],"error":null,"id":"curltest"}

```

### 7. 根据交易ID取得交易明细
```
命令行请求：
curl --user bitbs123 --data-binary '{"jsonrpc": "1.0","id": "curltest","method": "gettransaction","params": ["jhsgabnzxghzhhd"]}' -H 'content-type: text/plain;' http://119.28.16.55:23114/

{
    "jsonrpc": "1.0",
    "id": "curltest",
    "method": "gettransaction",
    "params": [
        "jhsgabnzxghzhhd"   //交易ID一定要合法 才能导出交易记录
    ]
}


{"result":null,"error":{"code":-5,"message":"Invalid or non-wallet transaction id"},"id":"curltest"}

```


### 8. 查出所有的币以标签
```
命令行请求：
curl --user bitbs123 --data-binary '{"jsonrpc": "1.0","id": "curltest","method": "listreceivedbyaddress","params": []}' -H 'content-type: text/plain;' http://119.28.16.55:23114/

{
    "jsonrpc": "1.0",
    "id": "curltest",
    "method": "listreceivedbyaddress",
    "params": []
}

{"result":[],"error":null,"id":"curltest"}

```

### 9. 根据收款地址，提现比特币
```
命令行请求：
curl --user bitbs123 --data-binary '{"jsonrpc": "1.0","id": "curltest","method": "listreceivedbyaddress","params": []}' -H 'content-type: text/plain;' http://119.28.16.55:23114/
```

### 10. 设置手续费


