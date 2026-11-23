# Panel checker

Claude can now use your computer. This skill puts that to work on one of the most boring jobs in lead gen: clicking through every partner's panel to check statuses and FTDs.

Claude reads each panel, fills one status sheet, then compares it with your own export and flags every mismatch: leads that never arrived, FTDs you're missing and FTDs the partner doesn't show.

**Who can use Part 1:** Computer Use is in beta for Claude Team and Enterprise plans in Claude Desktop, rolling out gradually. Part 2 (the comparison) works on any plan, and in ChatGPT too.

## What's in this folder

| File | What it is |
| --- | --- |
| `panel-checker-skill.zip` | The skill, ready to upload to Claude |
| `SKILL.md` | The skill's instructions, if you want to read them |
| `PROMPT.md` | Copy-paste prompts for other AI agents and for ChatGPT |
| `samples/lead-export.csv` | A fake lead export |
| `samples/panel-readings.csv` | A fake status sheet, as Claude would fill it from the panels |

## How to use it in Claude

1. Click `panel-checker-skill.zip` in the file list above, then the download button.
2. In Claude, go to **Customize > Skills**, click **+**, then **Create skill**, then **Upload a skill**, and choose the zip. Don't unzip it.
3. Log in to each partner panel in your browser yourself.
4. In Claude Desktop, start a chat and say: *"Check my panels for last week."* Attach your lead export.

## Safety, please read

- Claude only reads. It's told never to click anything that changes data.
- Claude never types your passwords. You log in first. It stops and asks at any login, two-factor prompt or captcha.
- Watch the first run, and check your partner agreements allow this kind of access.

## Try the comparison on the sample files first

Attach both sample files and ask for Part 2 only.

| Check | Correct result |
| --- | --- |
| Rows | 120 leads in the export, 117 rows in the panels, 116 matched |
| Never arrived | 4 leads: L-70018, L-70026 (Partner A), L-70063, L-70086 (Partner C) |
| FTDs you're missing | 3: L-70042, L-70077, L-70118. Worth $1,350 at $450 / $400 / $500 per partner |
| FTDs the panel doesn't show | 2: L-70080, L-70091. Worth $900 |
| Different status | 5: L-70002, L-70031, L-70057, L-70108, L-70111 |
| Unknown leads | 1: L-79999 (Partner B) |
| Matching exactly | 106 |

Partner prices for the sample: Partner A $450, Partner B $400, Partner C $500.

If the AI's numbers don't match, ask it to show the code it ran.

**A note on data.** Lead data is personal data. Check your data agreements before uploading it to any AI tool.

---

Made by [Alion](https://alion.app). Alion pulls statuses straight from partners' systems as they change, so nobody has to click through panels. Free for your first 100 leads a month.
