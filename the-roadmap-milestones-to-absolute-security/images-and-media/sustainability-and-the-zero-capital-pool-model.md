# Sustainability and the Zero-Capital Pool Model

A defining characteristic of <kbd><mark style="color:$danger;">Anzen Double Bet<mark style="color:$danger;"></kbd>'s first phase is its <kbd>`"Zero Capital"`</kbd> approach. The protocol does not contribute its own liquidity to the compensation pools. Instead, the pool for any given match is strictly limited to the total premiums collected from all users who purchased insurance for that match.

#### The Payout Pool Composition

In Phase 1, the pool is an aggregate of all fees collected from both sides **(those insuring "Team A not to lose" and those insuring "Team B not to lose")**. This design creates a symbiotic relationship where the winners of the insurance "bet" **(those whose team did not lose)** essentially fund the compensation for the losers.

In future phases (Phase 2), the protocol intends to implement <kbd><mark style="color:$success;">"auto-hedging,"<mark style="color:$success;"></kbd> where pools are segregated by team. In that model, the fees collected from Team A insurers would be used to purchase <kbd>"YES"</kbd> shares for Team B on <kbd><mark style="color:$primary;">Polymarket<mark style="color:$primary;"></kbd>, creating a more robust and scalable capital base.

#### The Waterfall Payout Mechanism

In scenarios where the total valid claims for compensation exceed the available funds in the match pool, the system employs a three-step priority distribution known as the "Waterfall".

* **Step 1:** Pro-rata Distribution by `Position Size` .All users who suffered a loss are initially allocated a share of the pool proportional to their original position size. If a user’s calculated share exceeds their maximum payout ceiling (e.g., 55% for Tier 1), they receive only the amount up to that ceiling. Any remaining funds from their pro-rata allocation are returned to the pool for the next step.
* **Step 2:** <kbd><mark style="color:yellow;">VIP Priority Allocation<mark style="color:yellow;"></kbd> If funds remain after Step 1, they are distributed exclusively to <kbd><mark style="color:yellow;">`VIP Pass`<mark style="color:yellow;"></kbd> holders who have "burned" their pass for that specific match. This ensures that <kbd><mark style="color:yellow;">`VIPs`<mark style="color:yellow;"></kbd> have the first claim on residual funds to help them reach their compensation ceilings.
* **Step 3:** Non-VIP Residual Allocation Any funds remaining after the <kbd><mark style="color:yellow;">`VIPs`<mark style="color:yellow;"></kbd> have been fully satisfied (or have reached their ceilings) are then shared among the non-VIP users until the pool is exhausted.

#### Analysis of a Waterfall Test Case

To understand the mechanics of the **Waterfall system**, consider a match pool containing 200 USDC with four users who suffered a loss :

| **User**   | **VIP** | **Position** | **Max Compensation Ceiling** |
| ---------- | ------- | ------------ | ---------------------------- |
| VIP #1     | Yes     | 100 USDC     | 60 USDC                      |
| VIP #2     | Yes     | 100 USDC     | 60 USDC                      |
| Non-VIP #1 | No      | 50 USDC      | 500 USDC (Theoretical)       |
| Non-VIP #2 | No      | 50 USDC      | 500 USDC (Theoretical)       |

**Stage 1 Distribution:**

The total position value of all losers is 300 USDC. The pool of 200 USDC is distributed proportionally:

* <kbd><mark style="color:yellow;">VIP #1:<mark style="color:yellow;"></kbd> Entitled to <kbd>200 x 100\300</kbd> = 66.67 $ USDC. Since the ceiling is 60, the user receives 60 USDC, and 6.67 USDC is returned to the pool.
* <kbd><mark style="color:yellow;">VIP #2:<mark style="color:yellow;"></kbd> Same as VIP #1 (receives 60 USDC, returns 6.67 USDC).
* Non-VIP #1: Entitled to <kbd>200 x 50\300</kbd> = 33.33 $ USDC. Since this is below the ceiling, they receive the full 33.33 USDC.
* Non-VIP #2: Same as Non-VIP #1 (receives 33.33 USDC).

**Stage 2 Distribution:**

The pool has a remaining balance of  6.67 + 6.67 = 13.33 $ USDC. Since the <kbd><mark style="color:yellow;">`VIP users`<mark style="color:yellow;"></kbd> have already reached their maximum ceilings in Stage 1, this step is skipped.

**Stage 3 Distribution:**

The remaining 13.33 USDC is split between the two non-VIP users who have not yet reached their ceilings. They each receive an additional \~6.67 USDC.

**Final Result:**

* <kbd><mark style="color:yellow;">VIPs:<mark style="color:yellow;"></kbd> 60 / 60 (100% of ceiling met).
* Non-VIPs: 40 / 40 (Shortfall of 460 USDC recorded).

The recorded shortfall for the non-VIPs is termed **"unmet compensation".** For <kbd><mark style="color:yellow;">VIP holders<mark style="color:yellow;"></kbd>, this unmet amount can be recovered at the end of the tournament round through the <kbd><mark style="color:yellow;">VIP Pool Settlement<mark style="color:yellow;"></kbd>.

#### The Windfall Profit of Draws

The sustainability of the Anzen model is significantly enhanced by the statistical probability of match draws. In professional football, approximately 24% of group stage matches end in a draw.

When a draw occurs, <kbd>"NO"</kbd> shares for both Team A and Team B settle at $1.00. This means that _neither_ side of the insurance products triggers a compensation event. In this scenario, the Anzen Protocol retains 100% of the premiums collected from all participants as profit.&#x20;

**This "windfall" allows the protocol to build reserves and sustain payouts during rounds with high volatility or frequent upsets.**

| **Match Result** | **Team A Outcome**  | **Team B Outcome**  | **Anzen Impact**     |
| ---------------- | ------------------- | ------------------- | -------------------- |
| Team A Wins      | Wins (Profit)       | Loses (Compensated) | Pays out Team B Pool |
| Team B Wins      | Loses (Compensated) | Wins (Profit)       | Pays out Team A Pool |
| Draw             | Wins (Profit)       | Wins (Profit)       | Retains 100% Fees    |

### The VIP Pass Ecosystem

The <kbd><mark style="color:yellow;">VIP Pass<mark style="color:yellow;"></kbd> is a central element of the Anzen economy, providing both utility and financial priority to dedicated users.

#### Pricing and the "Extra Life" Repurchase

<kbd><mark style="color:yellow;">`VIP Passes`<mark style="color:yellow;"></kbd> are sold on-chain with pricing that increases as the tournament progresses to reflect the higher stakes.

| **Tournament Round** | **VIP Pass Price (USDC)** | **"Extra Life" Price** |
| -------------------- | ------------------------- | ---------------------- |
| Group Stage          | $200                      | $100                   |
| Round of 32          | $400                      | $200                   |
| Round of 16          | $600                      | $300                   |

Users must **"burn"** their pass to apply its benefits to a specific match where they suffered a loss. A pass can only be burned for a match where the user actually lost money, ensuring that the burn mechanism is tied to a real insurance event.&#x20;

After burning a pass, the user can purchase an **"Extra Life"** for 50% of the original round price to maintain their VIP benefits for the remainder of the round.

#### The Cashback Mechanism

To incentivize participation and lower the risk of entering the <kbd><mark style="color:yellow;">`VIP tier`<mark style="color:yellow;"></kbd>, Anzen offers an 80% cashback on the VIP Pass price if the user does not burn the pass during the entire round.&#x20;

For example, **`if a user buys a $200 pass and their teams never lose, they receive $160 back at the end of the round. This mechanism effectively means the "cost of safety" for a lucky user is only 20% of the pass price.`**

###
