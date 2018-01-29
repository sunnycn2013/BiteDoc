[比特币相关资料](https://github.com/sunnycn2013/BiteDoc/blob/master/ziliao.md)


jsonrpc：RPC 版本
method ： 函数名
params： 请求入参数
id: 应该是networkdID  1代表

### 资料

[以太坊钱包：Geth使用教程](http://8btc.com/thread-29530-1-1.html)

[私有链的搭建](http://www.cnblogs.com/zl03jsj/p/6858928.html)

[Windows系统以太坊区块链私链的搭建启动、数据抓取、浏览器数据显示](https://bitshuo.com/topic/587d99af4dea36e72c1b3811)

[以太坊文档（中文版](https://www.51chain.net/portal/book/EthereumFrontierGuide/Commandlineinterfaceandoptions-120.html)

[以太坊（浏览器）](https://etherscan.io/)



###  官方 API
以太坊 JSON-RPC 
https://github.com/ethereum/wiki/wiki/JSON-RPC

以太坊 web3.js API 
 https://github.com/ethereum/wiki/wiki/JavaScript-API#web3js-api-reference

以太坊Management-APIs  (admin  debug   miner   personal    txpool)
https://github.com/ethereum/go-ethereum/wiki/Management-APIs


### 1.开辟钱包账户地址

```

{"jsonrpc":"2.0","method":"personal_newAccount", "params":[“12345”], "id": 1}


return json:
{"jsonrpc":"2.0","id":1,"result":"0x381309d3030e1882648668704124facf77970f25"}

```

### 2.取得账户列表


```
请求参数
{"jsonrpc":"2.0","method":"eth_accounts", "params":"[]", "id": 1}


return json:
{"jsonrpc":"2.0","id":1,"result":["0xead9bbbdd263d03bf8e1f0611b7ae0d7fa3abc55","0x68bdd512eae5425987ff5a7d892e30bdecb912c9","0xff97cfaf08abf18aaab69ff8d038ca7101acde0f","0x6f61eac3f037864eec29831a4a18aac41eec25bb","0x9c88b0e1d92c663e9e608ce6b2d0c9da88d4c7a9","0x8738bf660f98be83016579dbec72594debd7a45a"]}
执行

```

### 3.取得钱包相关信息 余额



 ```
eth_getBalance()

获取钱包信息,传入参数时，获取信息余额

命令行请求：

{"jsonrpc":"2.0","method":"eth_getBalance","params":["0x91ba8f25e03f9a4765d87162dbd0849115faf0b3", "latest"],"id":1}



参数:
return json:{"jsonrpc":"2.0","id":1,"result":"0x38d7ea4c68000"}
余额（wei） 转成ETH

> web3.fromWei("0x38d7ea4c68000","ether")
"0.001"

### 4.查看当前矿费  eth_gasPrice

{"jsonrpc":"2.0","method":"eth_gasPrice","params":[],"id":1}

return json:{"jsonrpc":"2.0","id":1,"result":"0x14b8d03a00"}

0x14b8d03a00 

> web3.fromWei("0x14b8d03a00","ether")
"0.000000089"   （ETH）



mac：
./geth --rpc --rpcaddr "localhost" --rpcapi  "db,eth,net,web3,personal,admin,miner" --datadir "/Users/alibaba/Documents/ETH/geth/gethData"


./geth --rpc --rpcaddr "localhost" --rpcapi  "db,eth,net,web3,personal,admin,miner" --datadir "/usr/local/geth/geth-linux-amd64-1.7.3-4bb3c89d/gethData"

nohup geth --rpc --rpcaddr "localhost" --rpcapi  "db,eth,net,web3,personal,admin,miner" --datadir "/usr/local/geth/geth-linux-amd64-1.7.3-4bb3c89d/gethData" &

--rpccorsdomain *

geth --rpc --rpccorsdomain "*" --rpcapi  "db,eth,net,web3,personal,admin,miner" --datadir "/usr/local/geth/geth-linux-amd64-1.7.3-4bb3c89d/gethData"


curl -X POST --data '{"jsonrpc":"2.0","method":"web3_clientVersion","params":[],"id":67}' -H 'content-type: application/json;' http://localhost:8545


curl -X POST --data '{"jsonrpc":"2.0","method":"eth_getBalance","params":["0x91ba8f25e03f9a4765d87162dbd0849115faf0b3", "latest"],"id":1}' -H 'content-type: application/json;' http://localhost:8545

cd ~/
ETH RPC  可用API  
