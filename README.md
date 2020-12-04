# Ren protocol Subgraph

RenVM, an open protocol providing access to inter-blockchain liquidity for all decentralized applications. Brings BTC, BCH and ZEC to any Ethereum app.

# Networks and Performance
This subgraph can be used for Ren on mainnet, and all testnets. In order to run it for a testnet, the subgraph.yaml file will need to have the contract addresses changed to point to the correct address for each respective network.

## Brief Description of The Graph Node Setup

A Graph Node can run multiple subgraphs, and in this case it can have a subgraph for Mainnet and testnets. The subgraph ingests event data by calling to Infura through http. It can also connect to any geth node or parity node that accepts RPC calls (such as a local one). Fast synced geth nodes do work. To use parity, the `--no-warp` flag must be used. Setting up a local Ethereum node is more reliable and faster, but Infura is the easiest way to get started. 

These subgraphs has three types of files which tell the Graph Node to ingest events from specific contracts. They are:
* The subgraph manifest (subgraph.yaml)
* A GraphQL schema      (schema.graphql)
* Mapping scripts       (**Individual** - ACL.ts, constants.ts, EVMScriptRegistry.ts, Finance.ts, Kernel.ts, TokenManager.ts, Vault.ts, Voting.ts | **Network** - DAOFactory.ts, ENSResolverFIFS.ts)

This repository has these files created and ready to compile, so a user can start this subgraph on their own. The only thing that needs to be edited is the contract addresses in the `subgraph.yaml` file to change between Rinkeby or Mainnet. If you are indexing a different Individual-DAO-Subgraph, you will have to grab the contract addresses that are relevant to that subgraph. 

The [getting started guide](https://github.com/graphprotocol/graph-node/blob/master/docs/getting-started.md) has in depth details on running a subgraph. 
