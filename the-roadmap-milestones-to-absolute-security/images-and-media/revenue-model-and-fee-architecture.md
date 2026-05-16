# Revenue Model and Fee Architecture

The protocol utilizes a tiered fee structure designed to correlate the insurance premium with the inherent risk of the underlying position. The risk is quantified by the entry price of the `"NO"` shares on <kbd><mark style="color:blue;">Polymarket<mark style="color:blue;"></kbd>; a higher price indicates a lower risk of the team losing, and thus a lower insurance premium.

#### Standard (Non-VIP) Fee Schedule

General users are categorized into tiers based on their entry price at the time of insurance purchase.

| **Tier**         | **NO Share Price (Entry)** | **Insurance Premium (% of Position Value)** |
| ---------------- | -------------------------- | ------------------------------------------- |
| Tier 1 — Premium | $ > 0.65 $                 | 10% – 15%                                   |
| Tier 2 — Lite    | $0.50 – $$ $0.64$ $$       | 15% – 18%                                   |
| Excluded         | $ < 0.50 $                 | Coverage Not Available                      |

The fees are structured to decrease linearly as the `"NO"` share price increases, reflecting a sophisticated risk-adjusted pricing model that ensures the protocol is adequately compensated for taking on high-risk positions.

#### VIP Incentives and Dynamic Pricing

Holders of the <kbd><mark style="color:yellow;">Anzen VIP Pass<mark style="color:yellow;"></kbd> receive significant cost advantages. <kbd><mark style="color:yellow;">VIP users<mark style="color:yellow;"></kbd> benefit from a flat reduction of 2.5 percentage points compared to the non-VIP schedule. For example, if a standard user pays a 15% premium, a <kbd><mark style="color:yellow;">VIP user<mark style="color:yellow;"></kbd> would only pay 12.5%.

Furthermore, the protocol implements a dynamic <kbd>"in-game"</kbd> surcharge to account for increasing certainty as the match progresses:

* **15th to 45th Minute:** Non-VIP users must pay an additional +2.5% surcharge on top of their base fee.
* **VIP Exemption:** <kbd><mark style="color:yellow;">VIP Pass<mark style="color:yellow;"></kbd> holders are entirely exempt from this in-game surcharge, allowing them to hedge later in the first half at the base rate.
* **Halftime Closing:** At the 45th minute, the portal for purchasing insurance closes for all users.
