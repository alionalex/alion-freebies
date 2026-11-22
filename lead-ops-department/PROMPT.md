# Lead ops department: prompt version

For ChatGPT, Gemini or any AI that doesn't use Claude skills.

**How to use it:** attach your files, then copy the block for the role you need and paste it. Each block works on its own.

Rules every block includes: use code if you can and never estimate, say which columns you used, clean emails and phones before matching, and start with a short summary.

---

## Data checker

```
Act as my data checker. I'm attaching my files. Today is [DATE].

Checks a lead export is clean enough to work with, before any other role runs.

**Needs:** Lead export.

Rules:
- List every column and what you think it holds. Flag missing columns that other roles need: lead ID, created date, sent date, partner, status, payout, email, phone.
- Count emails with spaces or capital letters, phones written with a leading 00, empty statuses, "New" statuses, and rows where the sent date is before the created date.
- Do not fix anything yet. Report it.

Give me:
1. A one-line verdict: ready, or what to fix first.
2. A table of each check and its count.
3. Which roles will be affected by each problem.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Duplicate checker

```
Act as my duplicate checker. I'm attaching my files. Today is [DATE].

Finds the same person sent more than once, often to different partners.

**Needs:** Lead export.

Rules:
- Two rows are the same lead if they share an email or a phone after cleaning.
- The earliest row by created date is the original. Every later match is a duplicate.

Give me:
1. The number of duplicates, split into email matches and phone-only matches.
2. A table: duplicate ID, original ID, what matched, the partner of each, the status of each.
3. Every person sent to two different partners.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Fraud analyst

```
Act as my fraud analyst. I'm attaching my files. Today is [DATE].

Flags leads that look fake before they cost you money or partner trust.

**Needs:** Lead export (with IP and form time if you have them).

Rules:
Flag a lead if any of these is true:
- the email domain is a disposable inbox (mailinator.com, 10minutemail.com, guerrillamail.com, tempmail.com, yopmail.com, trashmail.com, or any other you recognise as disposable, named)
- the form was filled in under 5 seconds
- 3 or more leads came from the same IP within 24 hours
If a column is missing, skip that check and say so.

Give me:
1. The number of flagged leads and how many each rule caught.
2. Clusters: the same IP or source behind several flagged leads, with times.
3. The sources with the most flagged leads.
4. A short list of what to do: block, ask the source, or watch.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Status chaser

```
Act as my status chaser. I'm attaching my files. Today is [DATE].

Finds leads your partners never sent a status back for, and writes the follow-up.

**Needs:** Lead export.

Rules:
- No status means the status is empty, "New", "Pending" or "Sent".
- Only count leads sent more than 5 days before today.

Give me:
1. The total and the count per partner.
2. A table: lead ID, partner, sent date, days since sent, current status.
3. A short, polite message per partner listing the lead IDs.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Status mapper

```
Act as my status mapper. I'm attaching my files. Today is [DATE].

Maps each partner's own status names to one standard list.

**Needs:** A list of raw status names per partner (or the lead export).

Rules:
Standard list: No answer, Call back, Not interested, Invalid, Duplicate, FTD.
- Map every raw name to one standard status.
- If a name could mean two things, say so and ask. Do not guess.

Give me:
1. A mapping table: partner, raw name, standard status.
2. Names you could not map, with your question.
3. A note on which partners use names that hide useful detail.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Cap planner

```
Act as my cap planner. I'm attaching my files. Today is [DATE].

Shows which partners will hit their caps next week and where the extra leads should go.

**Needs:** Lead export, partner caps (partner, daily cap, reset time zone).

Rules:
- Use the last 7 full days before today, by sent date.
- For each partner count the days the leads sent reached or went over the cap.

Give me:
1. A table: partner, cap, average sent per day, days at or over cap, average room left.
2. Partners likely to cap out (at or over cap on 3 or more of 7 days).
3. Where to move the extra volume.
4. Each partner's reset time zone.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Routing planner

```
Act as my routing planner. I'm attaching my files. Today is [DATE].

Suggests next week's split across partners based on what each lead was actually worth.

**Needs:** Lead export, partner contracts, partner caps.

Rules:
- Use the last 28 full days by sent date.
- Value per lead = FTDs x the contract price on the FTD date, divided by leads sent.
- Suggested split = each partner's value per lead as a share of the total.
- Check the split against caps using the average leads per day. Flag any partner that would go over.

Give me:
1. A table: partner, leads, FTDs, value per lead, suggested split %, leads per day at that split, cap.
2. The change from the current split, in one sentence per partner.
3. Any cap problems with the new split.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Dead lead reshuffler

```
Act as my dead lead reshuffler. I'm attaching my files. Today is [DATE].

Finds dead leads worth sending to a different partner.

**Needs:** Lead export.

Rules:
- Worth resending: "No answer", "Voicemail", "Call back" or "Not interested", sent at least 3 days before today.
- Exclude "Invalid number", "Wrong person", FTDs, anything in progress, duplicates (later rows that match an earlier lead) and any lead the fraud analyst would flag.
- Ask about statuses not listed here.

Give me:
1. The count by status, by country and by source.
2. For each lead, the partners it already went to.
3. A CSV of the list, if you can create files.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Partner scorecard

```
Act as my partner scorecard. I'm attaching my files. Today is [DATE].

Ranks your partners on the numbers that matter.

**Needs:** Lead export.

Rules:
- For the whole period in the file.
- Hours to status = time from sent to the first status update, for leads that have a real status.
- Payout per lead uses the payout as recorded.
- Leads with no status = status empty, "New", "Pending" or "Sent", sent more than 5 days before today.

Give me:
1. A table: partner, leads, FTDs, FTD rate, payout per lead, median hours to status, leads with no status.
2. A one-line verdict per partner: grow, keep, watch or cut, with the reason.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Partner onboarding

```
Act as my partner onboarding. I'm attaching my files. Today is [DATE].

Prepares everything to agree with a new partner before the first lead.

**Needs:** The partner's name, and anything you already know about the deal.

Rules:
- Cover: what counts as a valid lead, how their statuses map to yours, the daily cap and its time zone, payout terms and the dispute window, how statuses reach you, a test lead, and a contact for problems.
- Mark anything still unknown as [TO AGREE].

Give me:
1. A checklist with each item filled in or marked [TO AGREE].
2. A short first message to the partner asking for the missing items.
3. A test plan for the first lead.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Payout reconciler

```
Act as my payout reconciler. I'm attaching my files. Today is [DATE].

Compares your FTDs with the partner's report, lead by lead.

**Needs:** Lead export, partner FTD report.

Rules:
- Match by lead ID.
- An FTD in your file is a row with the status "FTD"; your amount is the payout column.

Give me:
1. Your count and total next to the report's, with the difference.
2. FTDs missing from the report.
3. FTDs in the report that you do not show as FTD, with your status.
4. FTDs with a different amount.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Contract keeper

```
Act as my contract keeper. I'm attaching my files. Today is [DATE].

Checks every payout against the contract price that was in force on that date.

**Needs:** Lead export, partner contracts (partner, price, valid from, valid to, payment terms, dispute window).

Rules:
- For each FTD, find the contract price valid on its FTD date (the status update date).
- Flag every FTD where the recorded payout differs from that price.

Give me:
1. The number of FTDs checked and how many are wrong.
2. A table: lead ID, partner, FTD date, recorded payout, contract price.
3. Each partner's payment terms and dispute window, with the deadline for this period's disputes.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Cost per FTD analyst

```
Act as my cost per ftd analyst. I'm attaching my files. Today is [DATE].

Shows what each FTD really cost, by campaign and ad set.

**Needs:** Ad spend export by ad set, lead export.

Rules:
- Clean names before matching (trim, lowercase, spaces, hyphens and underscores treated the same).
- Match on campaign and ad set.

Give me:
1. A table: campaign, ad set, spend, leads, FTDs, CPL, cost per FTD, revenue, profit.
2. The cheapest CPL and the cheapest cost per FTD, and whether they are different.
3. Ad sets losing money.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Invoice drafter

```
Act as my invoice drafter. I'm attaching my files. Today is [DATE].

Drafts the invoice for FTDs both sides agree on.

**Needs:** Lead export, partner FTD report, partner contracts.

Rules:
- Invoice only FTDs that are in both files AND where the report amount equals the contract price.
- Everything else goes to the dispute writer, not the invoice.

Give me:
1. Invoice lines per partner: lead ID, FTD date, amount.
2. The total per partner and overall.
3. A list of what was left out and why.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Dispute writer

```
Act as my dispute writer. I'm attaching my files. Today is [DATE].

Writes evidence-based disputes for money you are owed, and tells you where you are wrong.

**Needs:** Lead export, partner FTD report, partner contracts.

Rules:
- Claim FTDs missing from the report, at the contract price.
- Claim FTDs the partner paid below the contract price, for the difference.
- If your own recorded payout is wrong and the partner paid the contract price, do not claim it. List it as your error to fix.
- Include lead IDs, sent times and your status dates as evidence.

Give me:
1. The total to claim per partner.
2. One message per partner: polite, specific, with the evidence.
3. Your own errors to fix, separately.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Meta gap checker

```
Act as my meta gap checker. I'm attaching my files. Today is [DATE].

Compares the leads Meta reports with the leads you actually received.

**Needs:** Meta export by day, lead export.

Rules:
- Normal gap = the median daily gap % before the change date you give (or 12 November 2026).
- Flag days more than 10 points above normal. Three or more in a row = the gap opened. A single day = likely a tracking problem on your side.

Give me:
1. The normal gap, the gap since it opened and the day it opened.
2. The flagged days, split into "gap opened" and "single-day spikes".
3. Meta CPL vs real CPL before and after.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Source analyst

```
Act as my source analyst. I'm attaching my files. Today is [DATE].

Shows which sources and countries send leads that convert.

**Needs:** Lead export.

Rules:
- FTD rate = FTDs / leads, per source and per country.
- Call out any source with leads but no FTDs.

Give me:
1. A table by source and a table by country.
2. The best and worst source, with numbers.
3. Sources to pause or test further.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Compliance checker

```
Act as my compliance checker. I'm attaching my files. Today is [DATE].

Flags ad copy likely to get rejected or break advertising rules.

**Needs:** Ad copy (one ad per line or a CSV).

Rules:
Flag copy that:
- promises returns or profits ("guaranteed", fixed percentages)
- promises income ("earn $X a week")
- says there is no risk or no possible loss
- uses scarcity or urgency that is not real ("only 3 spots left")
- implies an endorsement by a celebrity or media outlet
Explain the reason for each flag. This is a first check, not legal advice.

Give me:
1. Each ad: OK or flagged, with the reason.
2. A safer rewrite for each flagged ad.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Weekly reporter

```
Act as my weekly reporter. I'm attaching my files. Today is [DATE].

Writes the weekly brief your team reads on Monday.

**Needs:** Lead export.

Rules:
- This week = the last 7 full days before today. Last week = the 7 days before that. Use the sent date.
- Payout uses the payout column.

Give me:
1. Leads, FTDs and payout this week and last week, with the change.
2. The same per partner.
3. One thing to look at today.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

## Forecaster

```
Act as my forecaster. I'm attaching my files. Today is [DATE].

Gives a simple forecast for next week from the last four weeks.

**Needs:** Lead export.

Rules:
- Use the last 4 full Monday-to-Sunday weeks, by sent date.
- Forecast = the average of those 4 weeks. Say clearly that it is an average, not a prediction model.

Give me:
1. A table of the 4 weeks: leads, FTDs, payout.
2. Next week's forecast for leads and FTDs.
3. Whether the trend is up, down or flat, and how sure you can be with this much data.

If you can run code, use it. Do not estimate. Clean emails (trim, lowercase) and phones (digits only, leading 00 = +) before matching. Tell me which columns you used. Start with a short summary in plain words.
```

---

Made by [Alion](https://alion.app). Alion runs many of these checks on every lead as it comes in. Free for your first 100 leads a month.
