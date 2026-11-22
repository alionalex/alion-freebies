# Routing planner

Suggests next week's split across partners based on what each lead was actually worth.

**Needs:** Lead export, partner contracts, partner caps.

## Rules
- Use the last 28 full days by sent date.
- Value per lead = FTDs x the contract price on the FTD date, divided by leads sent.
- Suggested split = each partner's value per lead as a share of the total.
- Check the split against caps using the average leads per day. Flag any partner that would go over.

## Give the user
1. A table: partner, leads, FTDs, value per lead, suggested split %, leads per day at that split, cap.
2. The change from the current split, in one sentence per partner.
3. Any cap problems with the new split.
