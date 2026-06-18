# UK Broadband Infrastructure Analysis (2018–2024)

An analysis of how fixed broadband has rolled out across the UK over six years, using real government data from OFCOM's Connected Nations reports and ONS geographic lookup tables. The goal was to take 14 separate raw CSV files and turn them into clear answers to four questions about coverage, performance, and regional fairness.

This one is pure data analysis, no machine learning. The work is in the wrangling and the interpretation.

## The four questions I looked at

1. How has coverage and performance changed over time?
2. Which local authorities had the fastest average download speeds in 2023?
3. Is there actually a correlation between gigabit (full fibre) availability and real download speeds?
4. Are some UK regions being left behind on gigabit rollout?

## What I found

Coverage trends: average superfast coverage jumped from the mid-40s% in 2018-19 to around 94% in 2020. A lot of that leap is OFCOM re-baselining their methodology rather than overnight construction, which is worth flagging rather than hiding. By the end of the period superfast coverage saturates around 97-98%, so basic access is more or less a solved problem.

The real story is capacity and fairness, not access. There's a clear positive correlation between gigabit infrastructure and actual speeds, which you'd expect but it's good to confirm. The bigger finding is a roughly 24.7% gap between the leading nations (England, Northern Ireland) and the ones lagging (Wales, Scotland). There's also an adoption gap: even in well-connected areas, plenty of users are still on slower connections, which points at affordability rather than availability.

## How it's built

The trickiest part was data prep. I loaded all 14 CSVs (7 coverage, 7 performance) with pandas, cleaned and standardised them, and merged them on geography so the years could actually be compared, which needed the ONS lookup tables to line up the geographic codes. Once the data was usable, each question is answered with the chart that fits it: line charts for the time trend, ranked bar charts for the top authorities, a scatter plot for the correlation, and a comparison against the national average for regional gaps.

## Tools

Python, pandas, matplotlib. Jupyter notebook.

## Data

OFCOM Connected Nations coverage and performance data (2018–2024) and ONS geographic lookup tables. All public government data.

## Running it

```bash
pip install pandas matplotlib
jupyter notebook uk_broadband_analysis.ipynb
```
