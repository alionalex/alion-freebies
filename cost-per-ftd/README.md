# Meta vs real leads

From 12 November 2026, Meta counts conversions on users' devices by default. Your reported leads may go up. The leads you actually get won't.

This free Claude skill compares Meta's lead count with the leads you received, day by day. It shows your normal gap, the day it opened, and what it does to your CPL.

The change doesn't apply in the EU or UK. The skill is still useful there, because it catches tracking problems on any day.

## What's in this folder

| File | What it is |
| --- | --- |
| `meta-lead-gap-skill.zip` | The skill, ready to upload to Claude |
| `SKILL.md` | The skill's instructions, if you want to read them |
| `PROMPT.md` | The same thing as a copy-paste prompt, for ChatGPT or any other AI |
| `samples/sample-meta-daily-export.csv` | A fake Meta Ads export, by day |
| `samples/sample-lead-export.csv` | A fake lead export to test with |

## How to use it in Claude

1. Click `meta-lead-gap-skill.zip` in the file list above, then click the download button (the arrow on the right).
2. In Claude, open **Settings**, find **Skills** and upload the zip. Don't unzip it first.
3. Start a chat, attach both files, and ask: *"Are Meta's lead numbers real?"*

## How to use it anywhere else

Open `PROMPT.md`, copy the prompt, and paste it into ChatGPT or any AI that reads files, with both files attached.

## What you need

- **Your Meta Ads export, by day.** In Ads Manager: pick the date range, click **Breakdown**, then **By time**, then **Day**. Then **Reports → Export table data → CSV**.
- **Your lead export.** One row per lead you received, with the date and the campaign. From your CRM, tracker or lead platform.

## Try it on the sample files first

The sample data is simulated. It runs from 20 October to 25 November 2026, with the change on 12 November.

| Check | Correct result |
| --- | --- |
| Normal gap before 12 Nov | 4.1% (median daily gap) |
| Gap opened | 12 November |
| Gap from 12 Nov | 24.1% (1,825 Meta leads vs 1,470 received) |
| Extra leads Meta reported | 355 from 12 November |
| CPL | Meta CPL looks better: $21.00 before, $17.66 after. Real CPL barely moved: $22.40 before, $21.92 after |
| Single-day spike | 3 November: Meta 114, received 48. A tracking problem, not Meta |
| Per campaign | Leads_Main_Tier1 gap 23.8%, Leads_Lookalike_2pct gap 24.8% from 12 Nov |

If the AI's numbers don't match, ask it to show the code it ran.

**A note on data.** Lead exports contain personal data. Check your data agreements before uploading them to any AI tool.

---

Made by [Alion](https://alion.app). Alion counts every lead as it arrives, so you always have the real number. Free for your first 100 leads a month.
