# Operational Lifecycle and System Workflow

The administration and execution of the <kbd><mark style="color:$danger;">Anzen Position Protection<mark style="color:$danger;"></kbd> insurance follow a rigorous nine-step lifecycle to ensure transparency and security on-chain.

1. **Epoch Initiation:** The administrator creates a match epoch in the backend.
2. **Data Synchronization:** The system pulls live data from <kbd><mark style="color:$primary;">Polymarket<mark style="color:$primary;"></kbd> to track share prices and user positions.
3. **Policy Selection:** Users browse insurance tiers, select their coverage, and execute a USDC payment on-chain.
4. **Match Lock:** The insurance gate closes at the 45-minute mark.
5. **Phase Transition:** Upon match conclusion, the epoch moves from `PROCESSING` to `ENDED`.
6. **VIP Burn Window:** A 2-hour window opens  <kbd><mark style="color:yellow;">VIPs<mark style="color:yellow;"></kbd> to decide if they wish to burn their pass for that specific match result.
7. **Black Swan Verification:** The backend automatically identifies potential Black Swan events, which are then manually confirmed by the administrator.
8. **Settlement Calculation:** The system calculates the Waterfall distribution and end-of-round VIP settlements, generating a Merkle root for the results.
9. **On-chain Claiming:** The Merkle root is posted to the smart contract, allowing users to claim their funds at any time with no expiration deadline.

###
