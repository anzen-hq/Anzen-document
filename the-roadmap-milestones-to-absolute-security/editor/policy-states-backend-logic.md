# Policy States (Backend Logic)

The policy moves through an automated lifecycle to prevent double-spending and ensure sub-second finality on the Circle Arc Network:

`ACTIVE` → `PROCESSING` → `CLAIMABLE` → `CLAIMED`

| **Status** | **Meaning**                                                       |
| ---------- | ----------------------------------------------------------------- |
| ACTIVE     | Monitoring trades in real-time within the current epoch.          |
| PROCESSING | Epoch ended; backend is syncing final Hyperliquid data.           |
| CLAIMABLE  | Merkle root posted on-chain; user can trigger the payout.         |
| CLAIMING   | Transaction in progress (temporary state to prevent re-entrancy). |
| CLAIMED    | Funds successfully moved to the user’s wallet.                    |
| EXPIRED    | Policy concluded with no eligible loss or claim timeframe passed. |
