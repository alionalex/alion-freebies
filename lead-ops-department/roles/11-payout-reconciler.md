# Payout reconciler

Compares your FTDs with the partner's report, lead by lead.

**Needs:** Lead export, partner FTD report.

## Rules
- Match by lead ID.
- An FTD in your file is a row with the status "FTD"; your amount is the payout column.

## Give the user
1. Your count and total next to the report's, with the difference.
2. FTDs missing from the report.
3. FTDs in the report that you do not show as FTD, with your status.
4. FTDs with a different amount.
