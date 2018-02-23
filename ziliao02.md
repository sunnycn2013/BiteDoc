ziliao:


http://blog.csdn.net/ddffr/article/details/76549320  

阳 https://baijiahao.baidu.com/s?id=1588466421521137557&wfr=spider&for=pc  我是--参照这个弄的


<<<kind inside mad rule scissors dismiss abandon comfort then second myth dwarf>>>


 123
geth --rpc --rpcaddr "0.0.0.0" --networkid 123 --rpcapi  "db,eth,net,web3,personal,admin,miner"  --rpcport 8545 --datadir "D:\ETH"


geth --datadir data --networkid 123456 --rpc --rpccorsdomain "*" --nodiscover console




 curl -X POST --data '{"jsonrpc":"2.0","method":"web3_clientVersion","params":["0x91ba8f25e03f9a4765d87162dbd0849115faf0b3", "latest"],"id":1}' -H 'content-type: application/json;' http://localhost:8545



 eth.sendTransaction({from:eth.accounts[0],to:"0x112d86bfcdd6a7449642a18c41031965e603d39b",value:web3.toWei(3,"ether")})