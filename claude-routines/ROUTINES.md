# 7 Claude routines for lead gen

One routine for each day of the week. Each one is a copy-paste prompt. Attach the file it asks for, paste the prompt, and replace anything in [brackets].

They work in Claude, ChatGPT or any AI that reads files. If your AI can run code, the numbers will be exact.

---

## Monday. Weekly brief

**Attach:** your lead export (one row per lead, with partner, sent date, status and payout).

```
I'm attaching my lead export. Today is [DATE].

Write my weekly brief.

Rules:
- "This week" is the last 7 full days before today. "Last week" is the 7 days before that. Use the sent date.
- Count every row as a lead. An FTD is a row with the status "FTD". Payout is the payout column.
- If you can run code, use it. Do not estimate.

Give me:
1. Leads, FTDs, FTD rate and payout for this week and last week, with the change.
2. The same for each partner.
3. The partner that improved most and the one that dropped most, with numbers.
4. One thing I should look at today, in one sentence.

Keep it to one screen. Short sentences.
```

---

## Tuesday. Meta vs real leads

**Attach:** your Meta Ads export broken down by day, and your lead export.

```
I'm attaching my Meta Ads export (by day) and my lead export.

Compare the leads Meta reports with the leads I actually received, day by day.

Rules:
- If you can run code, use it. Do not estimate.
- Use the date only, not the time.
- The normal gap is the median daily gap % before [CHANGE DATE, or the first 14 days if none].
- Flag days where the gap % is more than 10 points above normal. Split them into "gap opened" (3 or more days in a row) and "single-day spikes" (likely a tracking problem on my side).

Give me:
1. A short summary: the normal gap, the current gap, and when it opened.
2. Meta CPL vs real CPL (spend / leads received), before and after the gap opened.
3. The flagged days.
4. Extra leads Meta reported that never arrived.
```

---

## Wednesday. Chase missing statuses

**Attach:** your lead export.

```
Using my lead export, find leads that never got a real status back from the partner. Today is [DATE].

Rules:
- A lead has no status if its status is empty, "New", "Pending" or "Sent".
- Only count leads sent more than 5 days ago.
- If you can run code, use it. Do not estimate.

Give me:
1. The total, and the count per partner.
2. A table: lead ID, partner, sent date, days since sent, current status.
3. A short, polite message for each partner asking for these statuses, with the lead IDs listed.
```

---

## Thursday. Duplicate sweep

**Attach:** your lead export.

```
Using my lead export, find duplicate leads.

Rules:
- Two rows are the same lead if they share an email or a phone number.
- Before comparing, clean the emails (trim spaces, make lowercase) and the phones (keep digits only, and treat a leading 00 the same as +).
- The earliest row is the original. Every later match is a duplicate.
- If you can run code, use it. Do not estimate.

Give me:
1. The number of duplicates.
2. A table: duplicate lead ID, original lead ID, what matched, the partner of each, the status of each.
3. Every case where the same person went to two different partners.
```

---

## Friday. FTD and payout check

**Attach:** your lead export and the partner's FTD report for the same period.

```
I'm attaching my lead export and the partner's FTD report.

Compare them, matching by lead ID.

Rules:
- In my export, an FTD is a row with the status "FTD". My expected payout is in the payout column.
- If you can run code, use it. Do not estimate.

Give me:
1. My FTD count and payout total next to the partner's, with the difference.
2. FTDs in my export that are missing from the report.
3. FTDs in the report that my export doesn't show as FTD, with my status for them.
4. FTDs in both files with a different amount.
5. A short, polite message to each partner listing their items, asking them to confirm.
```

---

## Saturday. Dead leads to resend

**Attach:** your lead export.

```
Using my lead export, find dead leads worth sending to a different partner. Today is [DATE].

Rules:
- Worth resending: the status is "No answer", "Voicemail", "Call back" or "Not interested", and the lead was sent at least 3 days ago.
- Not worth resending: "Invalid number", "Wrong person", any FTD, anything still in progress, and duplicates (same email or phone as an earlier row, after cleaning).
- Flag, but don't remove, any lead whose duplicate is still in progress with another partner.
- If you find statuses I haven't listed, ask me how to treat them. Don't guess.
- If you can run code, use it. Do not estimate.

Give me:
1. How many leads are worth resending, split by status.
2. The same count by country and by source.
3. For each lead, the partners it has already been sent to.
4. A CSV of the list, if you can create files.
```

---

## Sunday. Cap plan for next week

**Attach:** your lead export and a list of partner caps (partner, daily cap, the time zone the cap resets in).

```
I'm attaching my lead export and my partner caps. Today is [DATE].

Plan next week's caps.

Rules:
- Use the last 7 full days, by sent date.
- For each partner, count how many days the leads sent reached or went over the daily cap.
- If you can run code, use it. Do not estimate.

Give me:
1. A table: partner, daily cap, average leads sent per day, days at or over cap, room left per day on average.
2. Partners likely to cap out next week (at or over cap on 3 or more of the last 7 days).
3. Where to move the extra volume, based on room left.
4. A reminder of each partner's reset time zone, so nothing gets sent after a cap is full.
```

---

Made by [Alion](https://alion.app). Alion runs most of these checks on every lead as it comes in. Free for your first 100 leads a month.
