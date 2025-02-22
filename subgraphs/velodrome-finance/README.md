# Introduction on Velodrome Finance

## Business Summary
Velodrome is an AMM on optimism forked from Solidly (a Fantom AMM developed by Andre Cronje). 

Conceptually Velodrome or its predecessor Solidly functions similarly to Curve Finance. The business of the protocol can be summarised as follows:

- Liquidity providers provide liquidity in pairs of tokens into pools and earn weekly VELO emission 
- Users trade with the pools
- Stakers lock platform token VELO to get veVELO and vote weekly to direct emissions of VELO inflations to pools
- Stakers earn trading fees from the pools, VELO rebase rewards and external bribes provided by third-parties to incentivise voting of a particular pool

## Useful links

- Protocol:
  - https://app.velodrome.finance/
- Docs:
  - https://docs.velodrome.finance/
- Smart contracts:
  - https://docs.velodrome.finance/security#contract-addresses
- Discord: 
  - https://discord.com/invite/velodrome
  
## User Metrics

The user actions of Velodrome include:

- Deposit and withdraw of liquidity into pools
- Stake and unstake LP tokens
- Liquidity provider claim VELO rewards
- Swap
- Stake (lock) VELO into veVELO NFT and unstake
- Stakers vote weekly to decide emission allocation into pools
- Stakers claim rewards (trading fees, VELO rebase rewards)
- Stakers claim bribes (a future feature, as of now bribes are airdropped weekly)
- Add a bribe (probably not a smart contract feature yet)
 

## Financial Metrics

### TVL

> TVL of the Protocol = $\sum$ value of tokens in all pools

Whereas, 

> TVL of a pool = ($\sum$Token1 * PriceToken1) + ($\sum$Token2 * PriceToken2) 

### Volume 

> Volume = $\sum$ transacted value of all swaps

### Revenue

> Total Revenue (Protocol Revenue) = $\sum$ Fee rate * Volume

The fee rates are 0.02% for stable AMMs and 0.02% to 0.05% for variable AMMs, subject to governance vote. 

All the fees go to the stakers of VELO, therefore all revenue are protocol-side revenue.

### Rewards

#### Rewards for LPs

Liquidity providers earn the VELO emissions as voted weekly by the stakers of VELO (veVELO holders):

> LP Reward Rate of a pool = Rewards in VELO * VELO Price / TVL of that pool

The initial supply of $VELO is 400M. Total weekly emissions start at 15M $VELO (3.75% of the initial supply) and decay at 1% per week (epoch).

#### Rewards for Stakers

Stakers of VELO (holders of veVELO NFTs) receive rebase VELO rewards and bribes in other incentive tokens, on top of the trading fees generated in the pools they have voted for.

> Staker Reward Rate = Trading Fee Rate + Rebase VELO Rewards Rate + Bribes Rate

Whereas, for each epoch (7 days):

> Trading Fee Rate = $\sum\ Trading Fees (Revenue) from a pool / (veVELO voted for that pool in this epoch * VELO price) * 52

As veVELO is not tradable, VELO price is used to simulate the value of veVELO.

> Rebase VELO Rewards Rate = Total Rebase VELO Rewards for that epoch * VELO price / (Total veVELO outstanding * VELO price) * 52
- The weekly rebase amount is calculated with the following formula:
(veVELO.totalSupply ÷ VELO.totalsupply)³ × 0.5 × Emissions
- Reference: https://docs.velodrome.finance/tokenomics#emissions

> Bribes Rate = Value of bribes for a pool in an epoch / (veVELO voted for that pool in this epoch * VELO price) * 52

### Protocol owned liquidity
There's no protocol owned liquidity but there's a treasury. 