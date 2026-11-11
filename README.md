# Tare

A weight tracker and TDEE calculator in one HTML file, with no build step, no dependencies and no server.

## Features

**Weight**
- Log a weigh-in for any date. Logging the same date again updates it, and deleting an entry can be undone.
- A chart of daily weigh-ins with a 7-day moving-average trend line and an optional goal line.
- Date ranges of 30 days, 90 days, 6 months, 1 year or all, with a tooltip on hover or tap. In the chart, the arrow keys step through entries.
- Summary of the current trend weight, the change over 7 and 30 days, and the distance to your goal.
- CSV import and export.
- lb or kg, switchable at any time.

**TDEE**
- BMR from Mifflin-St Jeor, the revised Harris-Benedict, or Katch-McArdle (which needs body fat %).
- TDEE from five activity levels, plus BMI.
- Daily calorie targets from losing 2 lb a week to gaining 1 lb a week, with warnings for targets below BMR or under 1,200 kcal.
- A macro split: protein at 1.8 g per kg, fat at 25% of calories, carbohydrate for the rest.
- An estimated date for reaching your goal weight.

## Run it

Open `index.html` in a browser. Nothing else is needed.

## Publish on GitHub Pages

1. Create a new repository on GitHub and upload these files, or from this folder run:
   ```sh
   git init
   git add .
   git commit -m "Add Tare"
   git branch -M main
   git remote add origin https://github.com/<your-username>/tare.git
   git push -u origin main
   ```
2. In the repository, go to **Settings → Pages**. Under **Build and deployment**, set the source to **Deploy from a branch**, choose `main` and `/ (root)`, then save.
3. After a minute the app is live at `https://<your-username>.github.io/tare/`.

## Where your data lives

Entries are saved in your browser's `localStorage`. They stay on your device and are never uploaded, including to the GitHub repo. A different browser, a different device or clearing site data starts empty. To move your data, use **Export CSV** and **Import CSV** in the History panel.

### CSV format

Use one row per day, with the date as `YYYY-MM-DD` followed by the weight. A header row is optional. If the header mentions `kg` or `lb`, that unit is used. Otherwise the app's current unit applies.

```csv
date,weight_lb
2026-11-10,167.4
2026-11-11,166.0
```

## Notes

These numbers come from standard estimation equations and the rule of thumb of 3,500 kcal per lb (7,700 per kg). Real needs vary, so adjust after a few weeks of watching your trend. This is not medical advice.
