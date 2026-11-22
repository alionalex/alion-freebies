# Data checker

Checks a lead export is clean enough to work with, before any other role runs.

**Needs:** Lead export.

## Rules
- List every column and what you think it holds. Flag missing columns that other roles need: lead ID, created date, sent date, partner, status, payout, email, phone.
- Count emails with spaces or capital letters, phones written with a leading 00, empty statuses, "New" statuses, and rows where the sent date is before the created date.
- Do not fix anything yet. Report it.

## Give the user
1. A one-line verdict: ready, or what to fix first.
2. A table of each check and its count.
3. Which roles will be affected by each problem.
