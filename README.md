# client-go for local Docker

##init

```bash
$ docker run --rm --name ethereum-node \ 
-v ${PWD}/geth-local:/root/.ethereum \
-v ${PWD}/genesis.json:/opt/genesis.json \ 
ethereum/client-go init /opt/genesis.json
```

##run

```bash
$ docker run --rm --name ethereum-node \
-v ${PWD}/geth-local:/root/.ethereum \
-p 8545:8545 -p 30303:30303 ethereum/client-go \
--networkid "10" --nodiscover --mine --minerthreads 1 \
--rpc --networkid 3 --rpcport "8545" --rpcaddr "0.0.0.0" \
--rpccorsdomain "*" --rpcapi personal,web3,eth
```

##javascript console 

```bash
$ geth attach http://localhost:8545
```

(not work)

```bash
docker run --rm -it ethereum/client-go attach http://docker.for.mac.localhost:8545
```
