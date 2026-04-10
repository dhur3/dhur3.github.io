---
title: Professional Licenses Data Visualization
tools: [Python, Altair, Vega-Lite]
image: assets/pngs/your_thumbnail_image.png 
description: Interactive visualizations of Illinois professional licenses data.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Analysis of Illinois Professional Licenses

<a href="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/licenses_fall2022.csv" class="btn">The Data</a>
<a href="https://github.com/dhur3/dhur3.github.io/blob/main/python_notebooks/Workbook.ipynb" class="btn">The Analysis</a>

<br><br>

### Plot 1: License Issuance Trend by Status
For the first plot, I visualized the historical trend of license issuances divided by their current status. I chose a Stacked Bar Chart (`mark_bar` with `stack='zero'`) because it maintains a flat baseline, making it highly intuitive to compare exact issuance volumes year over year. For the design choices, I encoded the "Year" as Ordinal (`:O`) on the x-axis and the "Count" as Quantitative (`:Q`) on the y-axis. I encoded the "License Status" as Nominal (`:N`) for the color scheme, using the 'set2' categorical palette to clearly distinguish the different, unrelated statuses. On the analysis side in my Python notebook, I performed several data transformations: I converted the 'Effective Date' column to datetime objects to extract the "Year", filtered out historical outliers (keeping only years between 1970 and 2023), and used the `.groupby()` function to aggregate the total size/count of licenses per year and status.

### Plot 2: License Density by City and Status
For the second visualization, I created a Heatmap (`mark_rect`) to display the density of licenses across the top 15 most active cities. I used a Nominal (`:N`) encoding for both "License Status" on the x-axis and "City" on the y-axis. Crucially, the total "Count" was encoded as Quantitative (`:Q`) and mapped to the color saturation using the sequential 'blues' color scheme. I chose this specific sequential scheme because darker shades intuitively represent a higher quantitative volume/density of licenses. In my Python notebook, I transformed the data by using `.value_counts().head(15)` to identify the top 15 cities, filtered the main dataframe to include only those cities, and grouped by city and status to calculate the final counts.

**Interactivity Discussion:** To go beyond basic pan/zoom features, I implemented a Dropdown menu (`alt.binding_select`) tied to an `alt.selection_point` that filters BOTH charts simultaneously based on the "License Status". When a user selects a specific status from the dropdown, the unselected segments in the Stacked Bar Chart fade out (lowering opacity), while the Heatmap dynamically transforms to display only the data for that selected status. This interactivity makes the visualization much more clear and interesting; instead of being overwhelmed by all the data at once, the user can isolate a specific condition (like "Active" licenses) and simultaneously explore its historical trend (Plot 1) and its geographical concentration (Plot 2).

<br>

<vegachart schema-url="{{ site.baseurl }}/assets/json/licenses_chart_hw5.1.json" style="width: 100%"></vegachart>
