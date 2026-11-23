# Panel checker: prompt versions

## Part 1. For any AI agent that can use a browser

Log in to every partner panel yourself first. Then paste this:

```
I'm logged in to my partner panels in this browser: [LIST THE PANELS].
Date range: [FROM] to [TO].

For each panel, go to the page that lists leads or conversions, set the date range, and read every row (use pagination until there are no more rows).

Record for each lead: partner, lead ID (or the ID the panel shows), status as written, and the time you read it.

Rules:
- Read only. Never click anything that changes data (approve, reject, edit, delete, resend, payout, settings).
- Never type passwords or codes. If you see a login page, a two-factor prompt or a captcha, stop and ask me.
- Stay on these panels only.

Give me one table with the columns: partner, lead_id, panel_status, read_at. Then tell me how many rows you read per panel and anything you couldn't read.
```

## Part 2. For ChatGPT, Claude or any AI that reads files

Attach your status sheet and your lead export, then paste this:

```
I'm attaching my status sheet (what each partner's panel shows) and my lead export.

Compare them by lead ID. Clean IDs first. If you can run code, use it. Do not estimate.

Give me:
1. Never arrived: leads in my export that are in no panel.
2. FTDs I'm missing: FTD in the panel but not in my export.
3. FTDs the panel doesn't show: FTD in my export but not in the panel.
4. Different status: both have the lead, the status differs, neither is an FTD.
5. Unknown leads: in a panel but not in my export.

Start with a short summary: rows read, how many match, and the money at stake in 2 and 3. Then one table per type, and a short polite message per partner listing their items.
```

---

Made by [Alion](https://alion.app). Alion pulls statuses straight from partners' systems as they change. Free for your first 100 leads a month.
