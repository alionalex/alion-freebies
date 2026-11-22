# Lead ops department

A full lead ops team in one Claude skill. 20 roles, from fraud analyst to dispute writer, that work on the exports you already have.

You ask in plain words ("which partner should get more leads next week?") and the right role picks it up.

## The 20 roles

| # | Role | What it does |
| --- | --- | --- |
| 01 | Data checker | Checks your file is clean before anything else runs |
| 02 | Duplicate checker | Finds the same person sent twice, often to two partners |
| 03 | Fraud analyst | Flags disposable emails, 2-second forms and IP clusters |
| 04 | Status chaser | Finds missing statuses and writes the follow-up to each partner |
| 05 | Status mapper | Maps every partner's status names to one list |
| 06 | Cap planner | Shows who caps out next week and where to move volume |
| 07 | Routing planner | Suggests next week's split from what each lead was worth |
| 08 | Dead lead reshuffler | Finds dead leads worth sending to a new partner |
| 09 | Partner scorecard | Ranks partners on FTD rate, payout per lead and response time |
| 10 | Partner onboarding | Prepares everything to agree before the first lead |
| 11 | Payout reconciler | Compares your FTDs with the partner's report |
| 12 | Contract keeper | Checks every payout against the price in force that day |
| 13 | Cost per FTD analyst | Shows what FTDs really cost by ad set |
| 14 | Invoice drafter | Invoices only the FTDs both sides agree on |
| 15 | Dispute writer | Claims money owed with evidence, and flags your own errors |
| 16 | Meta gap checker | Compares Meta's lead count with the leads you received |
| 17 | Source analyst | Shows which sources and countries convert |
| 18 | Compliance checker | Flags ad copy likely to be rejected |
| 19 | Weekly reporter | Writes the Monday brief |
| 20 | Forecaster | Gives a simple forecast for next week |

Shortcuts: type **"Full audit"**, **"Monday"** or **"Month end"** to run several roles in a row.

## What's in this folder

| File | What it is |
| --- | --- |
| `lead-ops-department-skill.zip` | The skill, ready to upload to Claude |
| `SKILL.md` and `roles/` | The front desk and the 20 roles, if you want to read or edit them |
| `PROMPT.md` | Every role as a copy-paste prompt, for ChatGPT or any other AI |
| `samples/` | Fake files to test with (answers below) |

## How to use it in Claude

1. Click `lead-ops-department-skill.zip` in the file list above, then the download button (the arrow on the right).
2. In Claude, go to **Customize > Skills**, click **+**, then **Create skill**, then **Upload a skill**, and choose the zip. Don't unzip it. (Skills need code execution switched on.)
3. Start a chat, attach your files and ask, for example: *"Full audit. Today is 16 November 2026."*

## How to use it anywhere else

Open `PROMPT.md`, copy the block for the role you need, and paste it into ChatGPT or any AI that reads files, with your files attached.

## Try it on the sample files first

The sample data is simulated: 637 leads sent to 4 partners from 1 October to 15 November 2026. Use **16 November 2026** as today's date.

| Role | Correct result |
| --- | --- |
| 01 Data checker | 637 rows. 6 emails need cleaning, 6 phones start with 00, 7 empty statuses, 8 "New" statuses |
| 02 Duplicate checker | 12 duplicates (6 by email, 6 by phone only), each sent to a different partner |
| 03 Fraud analyst | 15 flagged. 9 come from one IP (185.220.101.47) within an hour on 9 Nov, all from Native-Feed-9 with disposable emails |
| 04 Status chaser | 15 leads. Partner B 8, Partner A 4, Partner C 3 |
| 05 Status mapper | Every raw name maps to the standard list. "Hung up" (Partner D) is the one worth asking about |
| 06 Cap planner | Partner B (cap 3) is at or over cap on 4 of the last 7 days. Partner D has the most room |
| 07 Routing planner | Value per lead over 28 days: D $68.18, A $48.06, C $32.32, B $10.29. Suggested split: D 43%, A 30%, C 20%, B 6% |
| 08 Dead lead reshuffler | 397 leads worth resending (duplicates and fraud-flagged leads excluded) |
| 09 Partner scorecard | D leads on FTD rate (13.6%). B is slowest (median 41 hours to a status) with the most missing statuses |
| 10 Partner onboarding | No fixed answer. The checklist should cover all 7 items in the role file |
| 11 Payout reconciler | 59 FTDs ($26,450) vs 58 in the report ($25,750). 3 missing, 2 extra, 5 different amounts |
| 12 Contract keeper | 3 Partner B FTDs after 1 November recorded at $400. The contract price from 1 November is $350 |
| 13 Cost per FTD analyst | Cheapest CPL: PL_Scale / Retarget_30d ($16.67). Cheapest FTD: PL_Scale / Broad ($200) |
| 14 Invoice drafter | 54 agreed FTDs, $24,250 in total |
| 15 Dispute writer | Claim $1,450 (3 missing FTDs and 2 underpaid). The 3 Partner B differences are your own error, not a claim |
| 16 Meta gap checker | Normal gap 6.5%. Gap opened on 12 November (about 25% since). One spike on 22 October (tracking on your side) |
| 17 Source analyst | Native-Feed-9: 9 leads, 0 FTDs. By country, GB (10.3%) and PL (10.0%) convert better than DE (8.5%) |
| 18 Compliance checker | Flag AD-02, AD-04, AD-05, AD-07 and AD-08. AD-01, AD-03 and AD-06 are fine |
| 19 Weekly reporter | This week (9 to 15 Nov): 104 leads, 8 FTDs, $3,500. Last week: 106 leads, 10 FTDs, $4,650 |
| 20 Forecaster | Last 4 weeks average about 98 leads and 8.5 FTDs a week |

If the AI's numbers don't match, ask it to show the code it ran.

**A note on data.** Lead exports contain personal data. Check your data agreements before uploading them to any AI tool.

---

Made by [Alion](https://alion.app). Alion runs many of these checks on every lead as it comes in. Free for your first 100 leads a month.
