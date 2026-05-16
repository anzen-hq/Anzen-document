# VIP Pool Settlement: End-of-Round Decisions

The most complex and rewarding aspect of the <kbd><mark style="color:yellow;">VIP Pass<mark style="color:yellow;"></kbd> is the end-of-round settlement. This process aggregates funds from all VIP-related activities and redistributes them to those who experienced shortfalls in their match-level compensation.

#### Step 1: Capital Aggregation <mark style="color:yellow;">`(The VIP Treasury)`</mark>

At the end of a tournament round (e.g., the Group Stage), the protocol creates a <kbd><mark style="color:yellow;">VIP Pool<mark style="color:yellow;"></kbd> from two sources:

1. 100% of the value of all passes that were burned during the round.
2. 20% of the value of all passes that were _not_ burned (the portion retained after cashback).

For instance, if 40 people buy passes at $200 each (Total $8,000) and 30 people burn them, while 10 do not:

* Burned contribution: <kbd>$ 30 x 200 = 6,000 $ USDC.</kbd>
* Unburned contribution: <kbd>$ 10 x 200 x 20% = 400 $ USDC.</kbd>
* Total VIP Pool: 6,400 USDC.

#### Step 2: Quota Calculation

Each user's potential share of the pool is determined by the number of times they burned a pass.  <mark style="color:$success;">**`User Quota = User's Burn Count \ Total Burns in Round x (VIP Pool Total)`**</mark>&#x20;

This rewards users who were active and suffered multiple losses, as they contributed more "burns" to the system.

#### Step 3: HardCap Constraints (The Shortfall)

To ensure that the protocol only pays out what is truly "owed," a user's payout is capped by their total "shortfall" **(the sum of all unmet compensation from every match where they burned a pass)**. This is known as the HardCap.

#### Step 4: Final Payout and Redistribution

The actual amount received by a user is the minimum of their Quota and their HardCap:

<kbd><mark style="color:$success;">**Actual Payout = min(Quota, HardCap) $**<mark style="color:$success;"></kbd>

&#x20;If a user's Quota is larger than their HardCap, the excess funds are not retained by the protocol; instead, they are redistributed to other VIP users who still have a remaining HardCap (shortfall) until the pool is empty or everyone is fully compensated.
