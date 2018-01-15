[比特币相关资料](https://github.com/sunnycn2013/BiteDoc/blob/master/ziliao.md)


jsonrpc：RPC 版本
method ： 函数名
params： 请求入参数
id: 应该是networkdID  1代表



ETH RPC  可用API  

https://etherscan.io/

以太坊 JSON-RPC 
https://github.com/ethereum/wiki/wiki/JSON-RPC

以太坊 web3.js API 
 https://github.com/ethereum/wiki/wiki/JavaScript-API#web3js-api-reference

以太坊Management-APIs  (admin  debug   miner   personal    txpool)
https://github.com/ethereum/go-ethereum/wiki/Management-APIs


### 1.开辟钱包账户地址

{"jsonrpc":"2.0","method":"personal_newAccount", "params":[“12345”], "id": 1}


return json:
{"jsonrpc":"2.0","id":1,"result":"0x381309d3030e1882648668704124facf77970f25"}



### 2.取得账户列表


请求参数
{"jsonrpc":"2.0","method":"eth_accounts", "params":"[]", "id": 1}


return json:
{"jsonrpc":"2.0","id":1,"result":["0xead9bbbdd263d03bf8e1f0611b7ae0d7fa3abc55","0x68bdd512eae5425987ff5a7d892e30bdecb912c9","0xff97cfaf08abf18aaab69ff8d038ca7101acde0f","0x6f61eac3f037864eec29831a4a18aac41eec25bb","0x9c88b0e1d92c663e9e608ce6b2d0c9da88d4c7a9","0x8738bf660f98be83016579dbec72594debd7a45a"]}
执行



### 4.取得钱包相关信息 余额



 ```
eth_getBalance()

获取钱包信息,传入参数时，获取信息余额

命令行请求：

{"jsonrpc":"2.0","method":"eth_getBalance","params":["0x407d73d8a49eeb85d32cf465507dd71d507100c1", "latest"],"id":1}


return json:{"jsonrpc":"2.0","id":1,"result":"0x0"}



