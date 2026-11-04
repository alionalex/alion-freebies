# Cost per FTD: prompt version

For ChatGPT, Gemini or any AI that doesn't use Claude skills. Upload both files, then paste this:

```
I'm attaching two files:
1. My ad spend export (spend and leads per campaign and ad set).
2. My lead export (one row per lead, with the campaign and ad set it came from, its status and the payout for FTDs).

Work out what each FTD actually cost.

Rules:
- If you can run code, use it. Do not estimate.
- Tell me which columns you used. If one is missing, ask me.
- An FTD is a lead with the status "FTD". If my file uses another word, ask me first.
- Names don't always match between the files. Before matching, trim spaces, make everything lowercase, and treat spaces, hyphens and underscores as the same.
- Match on campaign and ad set together.

For each ad set and each campaign, give me: spend, platform leads, leads received, FTDs, platform CPL, real CPL (spend / leads received), cost per FTD, revenue (sum of FTD payouts) and profit (revenue minus spend). Add a total row.

Then tell me, with numbers:
1. The ad set with the cheapest real CPL and the one with the cheapest cost per FTD, and whether they're different.
2. Ad sets losing money, biggest loss first.
3. Ad sets with spend but no leads received (likely broken tracking).
4. Ad sets where the platform reported more than 5% more leads than I received.
5. Leads that matched no ad set, with their FTDs and revenue.
6. Every name mismatch you had to fix.

Start with a short summary: total spend, total FTDs, overall cost per FTD, total profit, and the one thing I should act on.
```
