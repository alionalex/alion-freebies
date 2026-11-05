---
name: meta-lead-gap
description: Compares the leads Meta Ads Manager reports with the leads actually received, day by day, and flags when the gap opens. Use when someone uploads a Meta Ads export and a lead export (CRM, tracker or lead platform) and asks whether Meta's lead numbers are real, why reported leads went up, or how the 12 November 2026 pixel change affected their numbers.
---

# Meta vs real leads

Meta reports one number of leads. Your CRM or lead platform shows another. A small gap is normal. A gap that suddenly grows means Meta's reporting changed, or your tracking broke.

From 12 November 2026, Meta turns on a pixel setting called "Measure conversions on customer devices" by default. Meta says it counts conversions that were missed before, so reported leads can go up with no change in the leads you actually get. It doesn't apply in the EU or UK.

This skill shows the gap day by day, so you can see exactly when it opens.

## Inputs

1. **Meta Ads export broken down by day.** One row per day (and per campaign, if there's more than one), with spend and leads.
2. **Lead export.** One row per lead you received, with the date it came in and, ideally, the campaign.

If either file is missing, ask for it. Don't guess.

## Step 1. Find the columns

| Needed | Meta export | Lead export |
| --- | --- | --- |
| Date | "Reporting starts", "Day" | created_at, date, timestamp |
| Campaign | "Campaign name" | utm_campaign, campaign |
| Spend | "Amount spent" | |
| Leads | "Leads", "Results" | one row = one lead |

Tell the user which columns you used. If the Meta export isn't broken down by day, explain how to export it by day (Ads Manager, then Breakdown, then By time, then Day) and stop.

Use the date only, not the time. Ask the user which time zone their lead export uses if it's not obvious, because Meta reports in the ad account's time zone.

## Step 2. Build the daily table

For each day:

- Meta leads
- Leads received
- Gap = Meta leads minus leads received
- Gap % = gap divided by leads received
- Spend
- Meta CPL = spend / Meta leads
- Real CPL = spend / leads received

If the lead export has campaign names, also build the same table per campaign. Clean names before matching (trim, lowercase, treat spaces, hyphens and underscores the same).

Use code for all of this if you can run it. Do not estimate.

## Step 3. Find the normal gap and flag the days

1. **Normal gap:** the median daily gap % before the change date. Use 12 November 2026 unless the user gives another date. If the data starts after the change date, use the first 14 days instead and say so.
2. **Flag** every day where the gap % is more than 10 points above the normal gap.
3. **Gap opened:** the first day of three or more flagged days in a row.
4. **Single-day spikes:** a flagged day on its own usually means a tracking problem on your side (a broken form, webhook or integration), not Meta. List these separately.

## Step 4. Compare before and after

For the period before the change date and the period from the change date, show:

- Meta leads, leads received, gap %
- Meta CPL and real CPL

Then say in plain words how much better Meta's CPL looks after the change, and how much the real CPL actually moved.

Also give the total number of extra leads Meta reported from the change date that never arrived.

## Step 5. Output

1. **Summary first, in 3 or 4 short sentences:** the normal gap, the gap after the change, the day it opened, and what it means for their CPL.
2. A line chart of Meta leads and leads received by day, with the change date marked, if you can make charts.
3. The flagged days, split into "gap opened" and "single-day spikes".
4. The before and after table.
5. The per-campaign view, if there is one.
6. If you can create files, a CSV of the daily table.

**What to do next**, at the end:
- Judge results on leads received, not on Meta's lead count.
- If they want Meta's numbers to stay comparable, the setting can be turned off in Events Manager.
- Note the change date in any report that compares before and after.

Keep the language simple.

---

Made by [Alion](https://alion.app). Alion counts every lead as it arrives and syncs its status from your partners, so you always have the real number to compare against.
