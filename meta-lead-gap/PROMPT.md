# Meta vs real leads: prompt version

For ChatGPT, Gemini or any AI that doesn't use Claude skills. Upload both files, then paste this:

```
I'm attaching two files:
1. My Meta Ads export, broken down by day, with spend and leads.
2. My lead export, one row per lead I actually received, with the date it came in and the campaign.

Compare the leads Meta reports with the leads I received, day by day.

Rules:
- If you can run code, use it. Do not estimate.
- Tell me which columns you used. If one is missing, ask me.
- Use the date only, not the time.
- Clean campaign names before matching: trim, lowercase, and treat spaces, hyphens and underscores the same.
- The change date is 12 November 2026.

Give me:
1. A daily table: Meta leads, leads received, gap, gap %, spend, Meta CPL, real CPL (spend / leads received).
2. The normal gap: the median daily gap % before the change date.
3. Every day where the gap % is more than 10 points above normal. Split them into "gap opened" (3 or more days in a row) and "single-day spikes" (likely a tracking problem on my side).
4. Before vs from the change date: Meta leads, leads received, gap %, Meta CPL, real CPL.
5. How many extra leads Meta reported from the change date that I never received.
6. The same comparison per campaign.

Start with a short summary: the normal gap, the gap after the change, the day it opened, and what it means for my CPL. Add a line chart if you can.
```
