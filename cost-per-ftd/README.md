# Cost per FTD

Ads Manager tells you what a lead cost. It doesn't tell you what an FTD cost.

This free Claude skill joins your ad spend export with your lead export. You get the real cost per FTD and the profit for every campaign and ad set. It often shows that the ad set with the cheapest leads is the most expensive one per FTD.

## What's in this folder

| File | What it is |
| --- | --- |
| `cost-per-ftd-skill.zip` | The skill, ready to upload to Claude |
| `SKILL.md` | The skill's instructions, if you want to read them |
| `PROMPT.md` | The same thing as a copy-paste prompt, for ChatGPT or any other AI |
| `samples/sample-meta-ads-export.csv` | A fake Meta Ads export to test with |
| `samples/sample-lead-export.csv` | A fake lead export to test with |

## How to use it in Claude

1. Click `cost-per-ftd-skill.zip` in the file list above, then click the download button (the arrow on the right).
2. In Claude, open **Settings**, find **Skills** and upload the zip. Don't unzip it first.
3. Start a chat, attach your ad spend export and your lead export, and ask: *"What did each FTD cost me?"*

## How to use it anywhere else

Open `PROMPT.md`, copy the prompt, and paste it into ChatGPT or any AI that reads files, with both files attached.

## What you need

- **Your ad spend export.** In Meta Ads Manager: pick the date range, break down by ad set, then **Reports → Export table data → CSV**.
- **Your lead export.** One row per lead, with the campaign and ad set it came from (usually your UTM fields), its status, and the payout for FTDs.

## Try it on the sample files first

Run it on the two files in `samples/`. The right answers:

| Check | Correct result |
| --- | --- |
| Totals | $20,300 spent, 56 FTDs from tracked ad sets, $362.50 per FTD, $22,900 revenue, $2,600 profit |
| Cheapest CPL | PL_Nov_Scale / Broad at $8.00 per lead, but $600 per FTD and a $950 loss |
| Cheapest FTD | PL_Nov_Scale / Retarget_30d at $150 per FTD, despite a $15 CPL |
| Losing money | UK_Test / Broad (−$1,500), PL_Nov_Scale / Broad (−$950), DE_Q4_Main / Broad_25-54 (−$850), UK_Test / Static_Carousel (−$800) |
| Broken tracking | UK_Test / Static_Carousel: $800 spent, 40 leads reported by Meta, 0 received |
| Unattributed | 24 leads with no UTMs, holding 2 FTDs and $850 revenue |
| Name fixes | 6 mismatches, for example "de_q4_main" vs "DE_Q4_Main" and "Lookalike 3pct" vs "Lookalike_3pct" |

If the AI's numbers don't match, ask it to show the code it ran.

**A note on data.** Lead exports contain personal data. Check your data agreements before uploading them to any AI tool.

---

Made by [Alion](https://alion.app). Alion tracks revenue per lead by source as leads come in, so you don't have to rebuild this every month. Free for your first 100 leads a month.
