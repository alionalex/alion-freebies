# Duplicate checker

Finds the same person sent more than once, often to different partners.

**Needs:** Lead export.

## Rules
- Two rows are the same lead if they share an email or a phone after cleaning.
- The earliest row by created date is the original. Every later match is a duplicate.

## Give the user
1. The number of duplicates, split into email matches and phone-only matches.
2. A table: duplicate ID, original ID, what matched, the partner of each, the status of each.
3. Every person sent to two different partners.
