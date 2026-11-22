# Meta gap checker

Compares the leads Meta reports with the leads you actually received.

**Needs:** Meta export by day, lead export.

## Rules
- Normal gap = the median daily gap % before the change date you give (or 12 November 2026).
- Flag days more than 10 points above normal. Three or more in a row = the gap opened. A single day = likely a tracking problem on your side.

## Give the user
1. The normal gap, the gap since it opened and the day it opened.
2. The flagged days, split into "gap opened" and "single-day spikes".
3. Meta CPL vs real CPL before and after.
