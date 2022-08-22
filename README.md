# Readme me audit

## Principle

The purpose of the swap is to use the taxes of the alliance tokens to distribute rewards when buying tokens.

For example, BABYAPE is taxed at 5% when purchased on PancakeSwap.
If we go through the new swap (AllianceSwap), there will be 0% taxes (because the swap is excluded from the fees). And so the 5% will be used to buy rewards tokens (BTC or ETH).
**Example :**
- With PancakeSwap you get 95% BABYAPE when you buy.
- With AllianceSwap you get 95% BABYAPE 2% BTC and 3% ETH when you buy.

## Code

- **AllianceRouter :** Based on the PancakeSwap v2 router (85% of the code is PancakeSwap code). This one allows to deviate the BNBs during the purchase to send them on the proxy.
- **AllianceProxy** : It receives the BNBs, buys the token of the alliance with + the tokens rewards. He is excluded from the fees of all the tokens of the alliance. It uses the basic PancakeSwap router to make purchases (0x10ED43C718714eb63d5aA57B78B54704E256024E)

## Requirements

- All tokens in the alliance must have their main liquidity pool in BNB
- All tokens used as rewards must have a liquidity pool in BNB
- Works only for purchases