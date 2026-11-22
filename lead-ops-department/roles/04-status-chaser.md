# Status chaser

Finds leads your partners never sent a status back for, and writes the follow-up.

**Needs:** Lead export.

## Rules
- No status means the status is empty, "New", "Pending" or "Sent".
- Only count leads sent more than 5 days before today.

## Give the user
1. The total and the count per partner.
2. A table: lead ID, partner, sent date, days since sent, current status.
3. A short, polite message per partner listing the lead IDs.
