### 一、本地部署geth

将geth.zip解压到D:/ETH 目录下， （D：/ETH/*）， 

![文件结构](https://github.com/sunnycn2013/BiteDoc/blob/master/bat.png?raw=true)

双击批处理文件即可启动JSON-RPC服务

eth.bat  文件：

```
geth --rpc --rpcaddr "0.0.0.0" --rpcapi  "db,eth,net,web3,personal,admin,miner"  --rpcport 23116 --datadir "D:\ETH"
```

双击后控制台如图：
![启动图](https://github.com/sunnycn2013/BiteDoc/blob/master/geth_start.png?raw=true)

### 二、测试本地geth服务

####  1. 获取余额

另启动一个控制台窗口，键入命令：

```
curl -X POST --data '{"jsonrpc":"2.0","method":"eth_getBalance","params":["0x91ba8f25e03f9a4765d87162dbd0849115faf0b3", "latest"],"id":1}' -H 'content-type: application/json;' http://localhost:8545
```



 得到一下

```
{"jsonrpc":"2.0","id":1,"result":"0x0"}
 
 值0x0，通过web3js中的 web3.toDecimal()即可进行进制转换（wei转10进制ETH）
 文档：https://github.com/ethereum/wiki/wiki/JavaScript-API#web3todecimal
```

####  2. 获取版本号


另启动一个控制台窗口，键入命令：

```
 curl -X POST --data '{"jsonrpc":"2.0","method":"web3_clientVersion","params":["0x91ba8f25e03f9a4765d87162dbd0849115faf0b3", "latest"],"id":1}' -H 'content-type: application/json;' http://localhost:8545
```

web3_clientVersion

 得到一下

```
{"jsonrpc":"2.0","id":1,"result":"Geth/v1.7.3-stable-4bb3c89d/darwin-amd64/go1.9.2"}
 
```


![调用结果](https://github.com/sunnycn2013/BiteDoc/blob/master/geth_cmd.png?raw=true)
跑通上述命令，本地环境应该测试通过，

<stong> 注意端口号 </stong>
