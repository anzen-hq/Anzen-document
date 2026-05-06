# Compensation Framework and Payout Dynamics

The compensation model is divided into two primary categories: <kbd>"Normal Events"</kbd> and <kbd>"Black Swan Events."</kbd> This distinction allows the protocol to provide basic protection for typical losses while offering enhanced coverage for extraordinary match circumstances.

#### Normal Event Payouts

In a standard match where the insured event occurs (the team loses), the compensation is capped based on the user's tier.

| **User Status** | **Tier 1 (Premium) Max Payout** | **Tier 2 (Lite) Max Payout** |
| --------------- | ------------------------------- | ---------------------------- |
| VIP             | 55% of Position Value           | 40% of Position Value        |
| Non-VIP         | 55% of Position Value           | 40% of Position Value        |

#### Black Swan Event Payouts

For events characterized by extreme unpredictability, <kbd><mark style="color:yellow;">`VIP Pass`<mark style="color:yellow;"></kbd> holders receive significantly elevated coverage ceilings, whereas non-VIP coverage remains unchanged

| **User Status** | **Tier 1 (Premium) Max Payout** | **Tier 2 (Lite) Max Payout** |
| --------------- | ------------------------------- | ---------------------------- |
| VIP             | Up to 100% of Position Value    | Up to 80% of Position Value  |
| Non-VIP         | 55% (No Change)                 | 40% (No Change)              |

To trigger a <kbd>"Black Swan"</kbd> classification, two conditions must be met concurrently:

1. **Prerequisite:** The <kbd>`"NO"`</kbd> share price of the losing side must have been $ > 0.75 $ at halftime. This metric indicates that the team was a heavy favorite to win or draw at the midpoint, making an eventual loss statistically **"surprising."**
2. **Qualitative Trigger:** The match must involve a specific extraordinary event, such as a first-half red card combined with a penalty, a "come-from-behind" victory occurring in the 90th minute or later, or a decisive own goal. These triggers require manual confirmation by the protocol administrator before the Black Swan payouts are authorized.
