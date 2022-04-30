# GATO SWAP Contract
GATO SWAP Contract forks the Pancake swap.
Change base fee to 1%.
### Installation
```sh
# Clone the repo
    git clone https://gitlab.com/merehead/gato/gato_swap_contracts.git
# Install all dependencies
    npm install
```
### Compile contract
```sh
npx hardhat compile
```
### Test contract
```sh
npx hardhat test
```
### Deploy contract
```sh
Factory BSC testnet deploy
npx hardhat run scripts/deploy_factory.js --network bsctestnet

Router BSC testnet deploy
npx hardhat run scripts/deploy_router.js --network bsctestnet
```
```sh
Factory BSC testnet deploy
npx hardhat run scripts/deploy_factory.js --network bscmainnet

Router BSC testnet deploy
npx hardhat run scripts/deploy_router.js --network bscmainnet
```
### Modifiers
##### onlyStopper
    Executes only by Stopper
##### onlyManager
    Executes only by Manager
##### isRunning
    Check for the contract running
### Functions
##### Mutable
    issueTokens() - issue the tokens every three months. onlyManager, isRunning
    distributeTokens(uint8 index) - distribute the tokens with index as following tokenomics. onlyManager, isRunning
            index 0 - PrivSaleWallet
                  1 - PubSaleWallet
                  2 - AdvisoryWallet
                  3 - TeamWallet
                  4 - EcoGrowthWallet
                  5 - CompanyWallet
                  6 - TreasuryWallet
                  7 - StakingRewardWallet
    burnTokens(uint256 amount) - burn the 10% of platform profits and commissions every quarter. onlyManager, isRunning
    pauseContract() - pause the contract. onlyStopper
    transfer(address to, uint256 amount) - transfer tokens to user. isRunning
        Approve must be done before transfer.
        to - address of receiver
        amount - transfered amount
    transferFrom(address from, address to, uint256 amount) - transfer tokens to user. isRunning
    Approve must be done before transfer.
        from - address of sender
        to - address of receiver
        amount - transfered amount
    approve(address spender, uint256 amount) - approve token for user. isRunning
        spender - address of spender
        amount - allowed amount
    increaseAllowance(address spender, uint256 addedValue) - increase the allowed amount. isRunning
        spender - address of spender
        addedValue - added amount
    decreaseAllowance(address spender, uint256 subtractedValue) - decrease the allowed amount. isRunning
        spender - address of spender
        subtractedValue - added amount
##### View
    name() - returns token diplay name(string)
    symbol() - returns token ticker(string)
    decimals() - returns token decimal(uint8) 
    allowance(address owner, address spender) - returns the allowed amount sent from owner to spender(uint256)
        owner - owner of token
        spender - address of spender
    totalSupply() - returns the total supply of token(uint256)
    balanceOf(address account) - returns the balance of user(uint256)
    issuanceTime() - returns the last issuance time(uint256)
    issuanceIndex() - returns the issuance count(uint)
    status() - returns the status of contract(bool)
        true: running
        false: paused
     
    
    
    





=======
# gato-swap-contract
This project is GATO swap contract for our own gato token on BSC
>>>>>>> 26a4bd67cef17c451011874b64759ffcfacf1bf7
