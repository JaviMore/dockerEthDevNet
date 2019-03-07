# DockerEthDevNet
A set of Docker images to create a local Ethereum network with three nodes and a monitor.
**NEVER USE THIS ON PRODUCTION**

The testnet consists out of multiple parts :
* 1 Bootnode - registers existing nodes on the network, discovery service.
* 2 Miners - Also called **sealers** with proof-of-authority. They validate the blocks. No RPC is exposed as they are required to be unlocked.
* 1 Node - This serves as **transaction relay** and is a fullnode that does not mine, is locked but has RPC exposed
* 1 Blockchain explorer - Lightweight web application to explore the blockchain through web application. 

## Miners / Geth Nodes
The RPC Ports of the nodes are mapped to your localhost, the addresses are:

* geth-dev-miner-1 : No RPC exposed
* geth-dev-miner-2: No RPC exposed
* geth-dev-node: [http://localhost:8545](http://localhost:8545)


## Blockchain Explorer
The blockchain explorer is a simple node.js web application being provided by a seperate container: geth-explorer. The application uses the web3 javascript API to fetch the data from `geth-dev-node` through RPC calls. The blockchain explorer can be found at [http://localhost:8080](http://localhost:8080).
