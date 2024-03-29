# uniswap-v2-contract

## Sample Scripts
### Install dependencies
```bash
yarn
```

### Compile contracts
```bash
yarn build
```

### Hardhat test
```bash
yarn test 
```

### Hardhat solidity-coverage
```bash
yarn test:cov
```

## SOP
### environment
#### localhost 
``` bash
yarn localhost

export ENV_FILE='./envs/env.localhost'
export NETWORK='localhost'
export WAIT_NUM=1
export GAS_PRICE=1
```

#### rinkeby
``` bash
export ENV_FILE='./envs/env.rinkeby'
export NETWORK_ID=4
export WAIT_NUM=1
export GAS_PRICE=3
```

#### eth
``` bash
export ENV_FILE='./envs/env.eth'
export NETWORK_ID=1
export WAIT_NUM=3
export GAS_PRICE=30
```

### script

#### deploy script
```bash
yarn run env-cmd -f $ENV_FILE yarn run hardhat contract:deploy --contract Example --gas-price $GAS_PRICE --args [] --network $NETWORK_ID --wait-num $WAIT_NUM

yarn run env-cmd -f $ENV_FILE yarn run hardhat upgradeableContract:deploy --contract ExampleUpgradeable --gas-price $GAS_PRICE ---args [] -wait-num $WAIT_NUM --network $NETWORK_ID
```

#### verify contract
```bash
yarn run env-cmd -f $ENV_FILE yarn run hardhat contract:verify --contract Example --network $NETWORK_ID

yarn run env-cmd -f $ENV_FILE yarn run hardhat upgradeableContract:verify --contract ExampleUpgradeable --network $NETWORK_ID
```