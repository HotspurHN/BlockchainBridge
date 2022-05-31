# Blockchain Bridge
## Contract example
### Rinkeby

**Erc20:** https://rinkeby.etherscan.io/address/0x15Cf2F3631461E15c35E1dC4e4a449e864520415#writeContract
**Bridge:** https://rinkeby.etherscan.io/address/0xF81b8567008F502E160d30Ae838CBc55d2938b31#writeContract

### BSC Testnet
**Erc20:** https://testnet.bscscan.com/address/0xAf4D39cfCe76E9e79e3b63F381fEbb53964EB300#writeContract
**Bridge:** https://testnet.bscscan.com/address/0x9c2215dd96a741c1AE17E51Bcc2722335E603050#writeContract

Tasks:
```
npx hardhat transfer --to 0xd88647bB0Eb39FF7bAaE7FEC1Bb75332A385dF6A --value 950000000000000000 --network rinkeby
npx hardhat approve --spender 0xd88647bB0Eb39FF7bAaE7FEC1Bb75332A385dF6A --value 50000000000000000 --network rinkeby
npx hardhat transferfrom --from 0x3C96E5Cfc585847aE330fa1A7f35647744d85F1D --to 0x3C96E5Cfc585847aE330fa1A7f35647744d85F1D --value 50000000000000000 --network rinkeby 

npx hardhat initothertoken --from rinkeby --to bscTestnet --network rinkeby
npx hardhat initothertoken --from bscTestnet --to rinkeby --network bscTestnet
npx hardhat swap --amount 100 --nonce 1 --token 0x15Cf2F3631461E15c35E1dC4e4a449e864520415 --network rinkeby
npx hardhat redeem --amount 100 --nonce 1 --chainid 4 --token 0xAf4D39cfCe76E9e79e3b63F381fEbb53964EB300 --signature 0x15eb3dcb35eed634e2c5ff6d0722c88f7d1cbbf3e115c8275a38a63c506dd304 --network bscTestnet
```

`.env` constants
```
PRIVATE_KEY=""
ALCHEMY_API_KEY=""
CONTRACT=""
STAKING_CONTRACT=""
ETHERSCAN=""
BSCSCAN=""
CONTRACT_BridgeRinkeby=""
CONTRACT_BridgeBSC=""
```

deploy 
`npx hardhat run --network rinkeby scripts/deploy.ts`