# Compensation Requirements (Business Logic)

To ensure the integrity of the risk pool, the following rules apply:

* **Net Realized Loss > 0:** Only closed positions are calculated. Profits and losses within the epoch are netted.
* **Post-Purchase Window:** Only trades opened _after_ the policy is timestamped on-chain are covered.
* **Epoch Confinement:** Positions must be closed before the epoch expires.
* **Coverage Ceiling:** Payouts never exceed the user's selected coverage cap.
  * _Example:_ 1,000 USDC coverage vs. 300 USDC loss = 300 USDC payout.
  * _Example:_ 1,000 USDC coverage vs. 1,500 USDC loss = 1,000 USDC payout.
