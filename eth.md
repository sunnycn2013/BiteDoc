[比特币相关资料](https://github.com/sunnycn2013/BiteDoc/blob/master/ziliao.md)

### 1.取得钱包相关信息 

 ```
eth_getBalance()

获取钱包信息,传入参数时，获取信息余额

命令行请求：
curl --user @bitbs --data-binary '{"jsonrpc": "1.0", "id":"curltest", "method": "eth_getBalance", "params": [] }' -H 'content-type: text/plain;' http://119.28.16.55:23114/


curl -X POST --data '{"jsonrpc":"2.0","method":"eth_getBalance","params":["0x407d73d8a49eeb85d32cf465507dd71d507100c1", "latest"],"id":1}'
http://119.28.16.55:23114/


geth --datadir data --networkid 1 --rpc --rpccorsdomain "47.94.220.244" --nodiscover console

geth --datadir data --networkid 1 --rpc --rpccorsdomain "*" --nodiscover console



curl http://api.map.baidu.com/telematics/v3/weather?location=%E5%8D%97%E6%98%8C

curl http://api.map.baidu.com/telematics/v3/weather?location=%E5%8D%97%E6%98%8C



curl -d "location=%E5%8D%97%E6%98%8C" "http://api.map.baidu.com/telematics/v3/weather"


curl -X POST --data '{"jsonrpc":"2.0","method":"web3_clientVersion","params":[],"id":67}'