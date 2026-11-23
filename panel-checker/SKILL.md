---
name: panel-checker
description: Uses Computer Use to read lead statuses and FTDs from each partner's panel into one sheet, then compares it with your lead export and flags every mismatch.
---

# Panel checker

Media buyers check partner panels by hand every day. This skill does it with Computer Use: it reads each partner's panel, copies what it sees into one status sheet, and compares that sheet with the user's own lead export.

It has two parts. Part 1 needs Computer Use (in Claude Desktop). Part 2 works in any chat: if the user already has a filled status sheet, skip to Part 2.

## Safety rules (always)

- **Read only.** Never click anything that changes data: approve, reject, edit, delete, resend, payout, settings. If unsure whether a button changes something, don't click it.
- **Never type passwords or codes.** The user logs in to every panel before you start. If you hit a login page, two-factor prompt, captcha or anything unexpected, stop and ask the user.
- **Stay on the panels the user names.** Don't open other sites or links.
- **Don't download or export personal data** unless the user asks. Copy only what the sheet needs.
- Remind the user once to check that their partner agreements allow this kind of access.

## Part 1. Read the panels (Computer Use)

1. Ask the user for: the list of partner panels, the date range, and confirmation that each panel is open in a browser tab and logged in.
2. For each panel, in order:
   - Go to the page that lists leads or conversions. Set the date range to match.
   - Read every row. Use the panel's own pagination or scrolling until there are no more rows.
   - Record, for each lead: partner, lead ID (or the identifier the panel shows, such as click ID or email), status as written in the panel, and the time you read it.
   - Count the rows you recorded and compare that with any total the panel shows. If they differ, say so.
3. Write everything into one status sheet with these columns: `partner, lead_id, panel_status, read_at`. Save it as a CSV if you can create files.
4. Tell the user how many rows you read per panel and anything you couldn't read.

## Part 2. Compare with the lead export

Inputs: the status sheet (from Part 1 or the user) and the user's lead export (lead ID, partner, status, payout).

Rules:
- Match by lead ID. Clean IDs first (trim spaces, same case).
- An FTD is a status of "FTD" (or the partner's own word for it, such as "Deposit" or "Converted"; ask if unsure).
- If you can run code, use it. Never estimate.

Find and list:
1. **Never arrived:** leads in the export that don't appear in any panel. These may not have reached the partner at all.
2. **FTDs you're missing:** FTD in the panel but not in your export. Money you may be owed. Show the payout from the user's contract if they give one.
3. **FTDs the panel doesn't show:** FTD in your export but not in the panel. Possible shaving or a mistake on either side.
4. **Different status:** both have the lead but the status differs (neither is an FTD).
5. **Unknown leads:** in a panel but not in your export.

## Output

1. A short summary first: rows read, how many match, and the money at stake in items 2 and 3.
2. One table per mismatch type.
3. One short, polite message per partner listing their items with lead IDs, asking them to confirm.
4. The status sheet and a mismatch CSV, if you can create files.

Use plain words and short sentences.

---

Made by Alion (alion.app). Alion pulls statuses straight from partners' systems as they change, so nobody has to click through panels.
