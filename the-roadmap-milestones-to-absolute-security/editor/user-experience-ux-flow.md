# User Experience (UX) Flow

1. **Onboarding:** Connect wallet → Select active Epoch → Purchase Insurance (requires only the premium in USDC; no massive deposits or "locked capital" required).
2. **Execution:** Trade on Hyperliquid as usual (Margin and position size are independent of the insurance policy).
3. **Settlement:** Epoch concludes → System calculates eligible realized losses → Immediate Payout enabled via Merkle proof.
4. **Recovery:** Users claim USDC directly from the contract.

#### Illustrative Example:

* **User Action:** Pays a 10 USDC premium for 1,000 USDC coverage.
* **Trading:** User operates on Hyperliquid with their own independent capital.
* **Result:** System records a 500 USDC Net Realized Loss during the epoch.
* **Recovery:** If the pool is in a Surplus state, the user receives 500 USDC immediately (the lower of loss vs. coverage).
* **The Advantage:** While traditional projects might spend a year researching "bad debt," Anzen users receive capital recovery in milliseconds.
