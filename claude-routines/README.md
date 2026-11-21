# 7 Claude routines for lead gen

One routine for each day of the week. Each one checks a different part of your lead business: your numbers, your partners, your duplicates, your caps.

You attach an export, type the day, and Claude does the check.

## What's in this folder

| File | What it is |
| --- | --- |
| `PROJECT-INSTRUCTIONS.md` | All 7 routines in one block, to paste into a Claude Project |
| `ROUTINES.md` | Each routine as a separate copy-paste prompt, for Claude, ChatGPT or any AI |
| `samples/` | Fake files to test with, plus the answers below |

## The 7 routines

| Day | Routine | What you attach |
| --- | --- | --- |
| Monday | Weekly brief | Lead export |
| Tuesday | Meta vs real leads | Meta export by day, lead export |
| Wednesday | Chase missing statuses | Lead export |
| Thursday | Duplicate sweep | Lead export |
| Friday | FTD and payout check | Lead export, partner FTD report |
| Saturday | Dead leads to resend | Lead export |
| Sunday | Cap plan for next week | Lead export, partner caps |

## Set it up in Claude (2 minutes)

1. In Claude, create a new **Project** called "Lead ops".
2. Open `PROJECT-INSTRUCTIONS.md`, copy everything, and paste it into the project's instructions.
3. Each day, start a chat in that project, attach your export and type the day, for example *"Monday"*.

## Use it anywhere else

Open `ROUTINES.md`, copy the routine for the day, and paste it into ChatGPT or any AI that reads files, with your export attached.

## Try it on the sample files first

Use 31 October 2026 as today's date. Tuesday uses its own two files (`meta-daily-export.csv` and `meta-lead-export.csv`) with 12 November 2026 as the change date. Every other day uses `lead-export.csv`, plus `partner-ftd-report.csv` on Friday and `partner-caps.csv` on Sunday.

| Day | Correct result |
| --- | --- |
| Monday | This week (24 to 30 Oct): 75 leads, 7 FTDs, $2,950. Last week: 76 leads, 9 FTDs, $3,450. Partner A improved most (1 to 4 FTDs). Partner C dropped most ($1,550 to $750) |
| Tuesday | Normal gap 4.1%. Gap opened on 12 November and is 24.1% after. 355 extra leads. One spike on 3 November (tracking, not Meta) |
| Wednesday | 18 leads with no status. Partner A 9, Partner B 5, Partner C 4 |
| Thursday | 14 duplicates, each sent to a different partner than the original |
| Friday | 40 FTDs ($16,200) in the export vs 39 ($15,500) in the report. 3 missing, 2 extra, 2 different amounts |
| Saturday | 150 leads worth resending |
| Sunday | Partner B is at or over its cap (3 a day) on 5 of 7 days. Partner D has the most room (cap 6, about 2.4 a day sent) |

If the AI's numbers don't match, ask it to show the code it ran.

**A note on data.** Lead exports contain personal data. Check your data agreements before uploading them to any AI tool.

---

Made by [Alion](https://alion.app). Alion runs most of these checks on every lead as it comes in. Free for your first 100 leads a month.
