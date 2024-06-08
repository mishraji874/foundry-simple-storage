## Foundry

**Foundry is a blazing fast, portable and modular toolkit for Ethereum application development written in Rust.**

Foundry consists of:

-   **Forge**: Ethereum testing framework (like Truffle, Hardhat and DappTools).
-   **Cast**: Swiss army knife for interacting with EVM smart contracts, sending transactions and getting chain data.
-   **Anvil**: Local Ethereum node, akin to Ganache, Hardhat Network.
-   **Chisel**: Fast, utilitarian, and verbose solidity REPL.

## Documentation

https://book.getfoundry.sh/

## Usage

### Initialize the project

```shell
$ forge --init
or
$ forge init --force
```

### Compile

```shell
$ forge compile
```

### Create

Create command is used to directly deploy the smart contract in the blockchain.

This command will help to hide the private key in the terminal and not visible to us in the history of the terminal.

```shell
$ forge create SimpleStorage.sol --rpc-url <rpc_url> --interactive
```

We can also directly write the private key using the command stated below:
```shell
$ forge create SimpleStorage.sol --rpc-url <rpc_url> --private-key <private_key>
```

### Build

```shell
$ forge build
```

### Test

```shell
$ forge test
```

### Format

```shell
$ forge fmt
```

### Gas Snapshots

```shell
$ forge snapshot
```

### Anvil

Use this command to run the local blockchain in the terminal
```shell
$ anvil
```

### Ganahce

We can also use ganache service to run a local blockchain in our system.

```shell
$ ganache-cli
```

### Deploy

This is the basic command to deploy your script.
```shell
$ forge script script/DeploySimpleStorage.sol
```

This is the better way to deploy your smart contract.

```shell
$ forge script script/DeploySimpleStorage.s.sol --rpc-url <your_rpc_url> --private-key <your_private_key>
```

Now, if you have to deploy the smart contract and also broadcast it then you the following command

```shell
$  forge script script/DeploySimpleStorage.s.sol --rpc-url <rpc_url> --broadcast --private-key <private_key>
```

### Cast

```shell
$ cast <subcommand>
```

This command is used to change the value from the given hash to numerical value.

```shell
$ cast --to-base <hash_input> dec
```

### Using .env file

```shell
$ source .env
$ forge script script/DeploySimpleStorage.s.sol --rpc-url $RPC_URL --private-key $PRIVATE_KEY
```

### Deploy your contract using thirdweb

Use the following command:

```shell
$ npx thirdweb deploy
```

Then, after that it will give the link in the terminal just open it in the browser and then do the further login using your wallet then it will deploy your smart contract on the blockchain.

### Interacting with smart contract using command line

We can further use the command line to interact with the smart contract with the following commands

```shell
$ cast send <contract_address> "<function_name_with_parameters>" <parameter_value> --rpc-url $RPC_URL --private-key $PRIVATE_KEY
```

After using this command then we have to check whatever we have given value to the function its apperaed or not, so we write the following code

```shell
$ cast call <contract_address> "<retrieving_function_name>"
```

This will generate the hash value. But its impossible for us to read it, so we use a new command to check whether the value coming is right or wrong.

```shell
$ cast --to-base <hash_generated> dec
```

### Help

```shell
$ forge --help
$ anvil --help
$ cast --help
```
