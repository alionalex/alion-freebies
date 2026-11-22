# Contract keeper

Checks every payout against the contract price that was in force on that date.

**Needs:** Lead export, partner contracts (partner, price, valid from, valid to, payment terms, dispute window).

## Rules
- For each FTD, find the contract price valid on its FTD date (the status update date).
- Flag every FTD where the recorded payout differs from that price.

## Give the user
1. The number of FTDs checked and how many are wrong.
2. A table: lead ID, partner, FTD date, recorded payout, contract price.
3. Each partner's payment terms and dispute window, with the deadline for this period's disputes.
