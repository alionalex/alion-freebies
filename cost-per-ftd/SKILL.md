---
name: cost-per-ftd
description: Works out what each FTD actually cost by joining an ad spend export (Meta Ads Manager or similar) with a lead export. Use when someone uploads ad spend and lead or conversion data and asks about cost per FTD, cost per conversion, real CPL, ROAS or profit by campaign, ad set or source.
---

# Cost per FTD

Ads Manager shows cost per lead. It doesn't know which leads became FTDs. This skill joins the two files so every campaign and ad set shows what an FTD really cost.

## Inputs

1. **Ad spend export.** One row per campaign or ad set, with spend and the platform's own lead count. A Meta Ads Manager CSV works as it is.
2. **Lead export.** One row per lead, with the campaign and ad set it came from (usually UTM fields), its status, and the payout for FTDs.

If either file is missing, ask for it. Don't guess.

## Step 1. Find the columns

Look for these, whatever they're called:

| Needed | Ad spend file | Lead file |
| --- | --- | --- |
| Campaign | "Campaign name" | utm_campaign, campaign |
| Ad set | "Ad set name" | utm_adset, utm_content, adset |
| Spend | "Amount spent" | |
| Platform leads | "Leads", "Results" | |
| Status | | status, partner_status |
| Payout | | payout, payout_usd, revenue |

Tell the user which columns you used. If a needed column is missing, say so and ask.

An FTD is a lead whose status is "FTD" (ignore case). If the file uses another word (for example "Deposit" or "Converted"), ask before counting.

## Step 2. Match the names

Campaign and ad set names rarely match exactly between the two files. Before matching, clean both sides:

- trim spaces
- make lowercase
- treat spaces, hyphens and underscores as the same character

So "DE_Q4_Main ", "de_q4_main" and "de-q4-main" all match.

Match on campaign and ad set together. If the ad spend file only has campaigns, match on campaign alone.

Use code for all of this if you can run it. Do not estimate.

## Step 3. Calculate, for each ad set and each campaign

- Spend
- Platform leads (what the ad platform reported)
- Leads received (rows in the lead export)
- FTDs
- Platform CPL = spend / platform leads
- Real CPL = spend / leads received
- Cost per FTD = spend / FTDs (show "no FTDs" when it's zero)
- Revenue = sum of FTD payouts
- Profit = revenue minus spend

Add a total row.

## Step 4. Point out what matters

Report these in plain words, with numbers:

1. **Cheapest CPL vs cheapest FTD.** Name the ad set with the lowest real CPL and the one with the lowest cost per FTD. If they're different, say so clearly. This is usually the most useful finding.
2. **Ad sets losing money.** Profit below zero, sorted by the size of the loss.
3. **Spend with no tracked leads.** Ad sets with spend but zero leads received. This usually means broken tracking, not a bad ad.
4. **Lost leads.** Where the platform reported noticeably more leads than were received (more than 5%).
5. **Unattributed leads.** Leads in the export that matched no ad set (including empty UTMs), with how many FTDs and how much revenue they hold.
6. **Name mismatches you fixed.** List each one, so the user can clean up their naming.

## Step 5. Output

1. A short summary first: total spend, total FTDs, overall cost per FTD, total profit, and the one finding they should act on.
2. The ad set table, then the campaign table.
3. The findings from step 4.
4. If you can create files, a CSV or spreadsheet of the ad set table.

Keep the language simple. No jargon beyond what's in the files.

---

Made by [Alion](https://alion.app). Alion tracks revenue per lead by source as leads come in, so this doesn't have to be a monthly job.
