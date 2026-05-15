# Revenue & Payout model

#### 1. The Core Revenue Engine.

The Anzen business model is built on a shared risk architecture. Unlike traditional insurance, which incurs high overhead, Anzen automates the split of every USDC premium the moment it is paid on-chain.

**Diagram: Premium Bifurcation**

Code snippet

```
graph TD
    User((Insured User)) -->|1. Pays Premium in USDC| Smart Contract
    Smart Contract -->|2. Automated Bifurcation| PP[Payout Pool]
    Smart Contract -->|3. Automated Bifurcation| Treasury
    
    Payout Pool -->|4a. Immediate Payout| User
    Treasury -->|4b. Operational Budget| team
    Treasury -->|4c. Reserve Growth| team
```

* **Who Pays:** High-frequency traders, prediction market participants, and DeFi protocols seeking embedded security stacks.
* Who Receives Fees:
  * The Community: Locked in the Payout Pool to ensure 100% of valid claims are met.
  * Team: Retained for protocol R\&D, security agent maintenance, and the Double Bet reserve fund.
* Volume Potential: For example, given Hyperliquid's $2.95 trillion trading volume in 2025 and the $11.6 trillion stablecoin transfer volume, even a 0.1% insurance penetration represents over $11 billion in premium volume.

***

#### 2. The Payout Waterfall (Shared Risk Model)

In the event of a market crash 10/10 or a protocol drain (Drift Protocol incident), Anzen uses a 3-step priority system to ensure the pool remains solvent even during extreme deficit states.

Diagram: The Payout Waterfall

Code snippet

```
graph TD
    Pool[Match/Epoch Payout Pool] -->|Step 1: Pro-Rata| All [All Losing Participants]
    All -->|If funds remain| VIP [VIP Pass Holders]
    VIP -->|If funds remain| NVIP [Non-VIP Overflow]
    
    subgraph "Settlement Logic."
    A --> B{Pool Surplus?}
    B -->|Yes| C
    B -->|No| D
    end
```

* **Who Receives Reimbursements:** Users who purchased insurance before a trade or protocol interaction.
* **Payout Speed:** Using the Malachite engine on Circle’s Arc, these transactions settle in <350ms.
* **Volume Impact:** While projects like Drift spend a year on research, Anzen restores capital immediately, allowing users to cycle that volume back into the market instantly.

***

#### 3. The "Draw" Windfall & Strategic Profit

A unique aspect of Anzen’s business model in sports prediction markets (Phase 2) is the statistical advantage of "Draws".

Diagram: The Draw Windfall Logic

| **Match Outcome** | **User Position** | **Insurance Trigger** | **Anzen Protocol Cash Flow**         |
| ----------------- | ----------------- | --------------------- | ------------------------------------ |
| Team A Wins       | NO Team A         | Triggered             | Payout issued to User                |
| Team B Wins       | NO Team B         | Triggered             | Payout issued to User                |
| Draw              | NO Team A & B     | NOT TRIGGERED         | 100% Premium Retention (Pure Profit) |

* The Math: In the 2026 cycle, roughly 24% of football matches end in a draw.
* Profitability: For every 100 insured matches, Anzen generates pure profit on \~24 of them without paying a single cent in claims, even though the users "won" their bets on Polymarket. This "Windfall Profit" is what funds the Double Chance guarantees for VIPs.

***

#### 4. Summary of Transaction Roles

* The Insured User: Pays the Premium (typically 1%–15% of position value) to buy peace of mind.
* The VIP Pass Holder: Pays a cycle-based fee ($200–$600) to gain priority in the waterfall and up to 100% coverage in Black Swan events.
* The Active AI Agents: Receive a performance fee from the Treasury for monitoring the Safety Factor and preventing exploits like the Drift hack.
* The Circle Arc Network: The settlement layer where all fees are denominated in USDC, ensuring dollar-denominated predictability for institutional volume.
