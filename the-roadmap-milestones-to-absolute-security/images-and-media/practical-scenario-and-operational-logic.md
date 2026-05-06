# Practical Scenario and Operational Logic

Consider a trader who believes that Real Madrid will not lose their upcoming match against Bayern Munich. On <kbd><mark style="color:blue;">`Polymarket`<mark style="color:blue;"></kbd>, this trader would acquire `"NO"` shares on the market titled **"Will Bayern Munich win?"**. This specific market settles as follows:

* `If Real Madrid wins or the match ends in a draw, the "NO" shares settle at $1.00, resulting in a profit for the trader.`
* `If Bayern Munich wins, the "NO" shares settle at $0.00, representing a total loss of the initial investment.`

<kbd><mark style="color:$danger;">`Anzen Double Bet`<mark style="color:$danger;"></kbd> intervenes in the event of the <mark style="color:$danger;">`"worst-case scenario"`</mark>—the victory of Bayern Munich. By purchasing insurance, the trader ensures that the Anzen Protocol will compensate a portion of their losses if the team they bet against (Bayern) actually wins.&#x20;

Consequently, the user is effectively **"protected"** across two scenarios (a win or a draw for their preferred team), mimicking the traditional <kbd><mark style="color:$danger;">"Double Bet"<mark style="color:$danger;"></kbd> effect.

#### Specificity of the Insurance Product

For every individual football match listed on the platform, the system generates exactly two distinct insurance products. This design is intentional and serves as a cornerstone for the protocol's internal sustainability

| **Insurance Product** | **Target Purchaser**                                       | **Compensation Trigger** |
| --------------------- | ---------------------------------------------------------- | ------------------------ |
| "Team A Not to Lose"  | Supporters of Team A or traders holding NO (Team B) shares | Team B Wins the Match    |
| "Team B Not to Lose"  | Supporters of Team B or traders holding NO (Team A) shares | Team A Wins the Match    |

The protocol intentionally excludes certain types of bets from its insurance coverage.&#x20;

Specifically, it does not sell insurance for `"YES"` shares (betting on a team to win directly) due to the excessively high probability of loss, nor does it cover <kbd>"Draw"</kbd> or <kbd>"No Draw"</kbd> specific markets, focusing instead on the core moneyline liquidity

