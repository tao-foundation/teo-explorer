# TEO TestNet Explorer
### TEO TestNet blockchain explorer

TEO Explorer is an Blockchain explorer built with NodeJS, Express and Parity. It does not require an external database and retrieves all information on the fly from a backend Ethereum-API based.

While there are several excellent Ethereum blockchain explorers available (etherscan, ether.camp and etherchain) they operate on a fixed subset of Ethereum networks, usually the mainnet and testnet. Currently there are no network agnostic blockchain explorers available. If you want to develop Dapps on a private testnet or would like to launch a private / consortium network, TEO Explorer will allow you to quickly explore such chains.

## Current Features
* Browse blocks, transactions, accounts and contracts
* View pending transactions
* Display contract internal calls (call, create, suicide)
* Upload & verify contract sources
* Show Solidity function calls & parameters (for contracts with available source code)
* Display the current state of verified contracts
* Named accounts
* Advanced transaction tracing (VM Traces & State Diff)
* View failed transactions
* Live Backend Node status display
* Submit signed Transactions to the Network
* Support for all [Bootswatch](https://bootswatch.com/) skins
* Accounts enumeration
* Signature verification
* Supports IPC and HTTP backend connections
* Responsive layout

## Planned features
* ERC20 Token support

Missing a feature? Please request it by creating a new [Issue](https://github.com/gobitfly/etherchain-light/issues) or [Here](https://github.com/trustfarm/teo-explorer/issues).

## Getting started

### Setup from source

Supported OS: Ubuntu 16.04

Supported backend nodes: rteo 

1. Setup a nodejs & npm environment
2. Install the latest version of the rteo client
3. Start parity using the following options: `rteo --chain=teotest --tracing=on --fat-db=on --pruning=archive`
4. Clone this repository to your local machine: `git clone https://github.com/trustfarm/teo-explorer --recursive` (Make sure to include `--recursive` in order to fetch the solc-bin git submodule)
5. Install all dependencies: `npm install` 
5-1. Install NVM (Node Version Manager) and use node version with > 8.x.x 
6. Rename `config.js.example` into `config.js` and adjust the file to your local environment
7. Start the explorer: `npm start`
8. Browse to `http://localhost:2888`

### Setup using docker

Build then run the container
```bash
docker build -t teoexplorer-testnet .
docker run -p 2888:2888 teoexplorer-testnet
```

Or directly bind the config.js file to avoid rebuilding the image
```bash
docker run -p "2888:2888" \
    -v "$(pwd)/config.js":/usr/src/app/config.js \
    teoexplorer-testnet
```

### Setup using docker-compose

```bash
docker-compose up
```
