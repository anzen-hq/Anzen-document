# USDC-Native Gas and Stable Fee Architecture

Anzen utilizes Arc's unique gas model to provide predictable insurance costs for users.

* **No Native Token Volatility:** Arc fees are denominated in USDC, eliminating the need for users to hold volatile native assets like ETH or SOL just to pay for transactions.
* **Dual-Decimal Implementation:** Native gas on Arc uses 18 decimals (mimicking ETH's structure for developer compatibility), while standard ERC-20 USDC on the chain uses 6 decimals.
* **Smoothed Fees:** The fee mechanism extends Ethereum's EIP-1559 by using weighted network demand moving averages, ensuring that businesses and insurance providers experience predictable dollar-denominated costs even during periods of high activity.
