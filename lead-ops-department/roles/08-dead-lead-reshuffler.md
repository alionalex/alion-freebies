# Dead lead reshuffler

Finds dead leads worth sending to a different partner.

**Needs:** Lead export.

## Rules
- Worth resending: "No answer", "Voicemail", "Call back" or "Not interested", sent at least 3 days before today.
- Exclude "Invalid number", "Wrong person", FTDs, anything in progress, duplicates (later rows that match an earlier lead) and any lead the fraud analyst would flag.
- Ask about statuses not listed here.

## Give the user
1. The count by status, by country and by source.
2. For each lead, the partners it already went to.
3. A CSV of the list, if you can create files.
