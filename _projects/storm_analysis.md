---
layout: page
title: "Nature's Fury: 2025 Storm Season"
description: "An interactive analysis of 2025 storm frequency and federal disaster declarations."
img: /assets/pngs/map-percentile-mntp-202501-202512.png
importance: 1
category: work
permalink: /projects/storm-analysis/
---

# 🌪️ Nature’s Fury: Unpacking the 2025 Storm Season
**By Jun Hur, Elle Crisostomo, Emily Fletcher, and Jaida Duson**

---

### **1. The Global Context: Warming Temperatures and Storm Activity**

Global warming is the leading cause of recorded changes in temperature across the globe. Temperatures continue to rise each year, and this is impacting storm activity significantly. Higher temperatures are causing storms to occur more rapidly, with more events predicted per year than ever expected. This shift affects all storm types regardless of geographic location, leading to increased rainfall, rising sea levels, and extreme heatwaves. As shown in the visualization below, the majority of the globe in 2025 experienced temperatures much warmer than average—a trend that is far from normal.

![Land & Ocean Temperature Percentiles](https://dhur3.github.io/assets/pngs/map-percentile-mntp-202501-202512.png)
*Source: NOAA National Centers for Environmental Information*

---

### **2. Why We "Double-Check" with FEMA Data?**

While meteorological data tells us how often a storm occurred, this FEMA chart demonstrates how much those storms actually impacted our communities. There is a critical gap between observing a weather event and officially declaring a national disaster. This FEMA disaster declaration chart represents a threshold of severity that demands federal intervention. By "double-checking" the weather frequency against this dataset, we can identify which events are truly the most dangerous to our infrastructure and safety. 

The dominance of categories like **"Severe Storm"** and **"Hurricane"** in these declarations shows that these are not just frequent weather patterns, but our primary national threats. It reminds us that these are the specific disasters we must prioritize in mitigation. Ultimately, this visualization moves us beyond simple weather tracking and provides a clear roadmap for where our attention and resources will save the most lives.

<div id="fema_chart"></div>

---

### **3. Explore Your State: Which Storms are Most Common?**

This interactive chart answers a critical question for every community: "Which weather hazards should we prioritize our resources for?" By using the **'Select State'** dropdown, you can explore the top 10 storm types for any state impacted in 2025. This provides essential data for both local governments and residents to determine where disaster mitigation budgets and emergency preparations can be utilized most efficiently. 

For instance, in **Illinois**, "Thunderstorm Wind" stands out as the overwhelmingly dominant threat with nearly 1,000 recorded events. While "Hail" is the second most frequent hazard with approximately 300 cases, it remains relatively minor compared to the sheer volume of high-wind events. Understanding these specific local signatures is the first step toward building resilient infrastructure tailored to the actual risks of each region.

<div id="state_chart"></div>

---

### **📚 Data Resources & Citations**

**Analysis Resources:**
* [View Jupyter Notebook on GitHub](https://github.com/dhur3/dhur3.github.io/blob/main/python_notebooks/Workbook_storm.ipynb)

**Data Sources:**
* **Storm Events Data:** NOAA National Centers for Environmental Information (2025). [Source Link](https://www.ncdc.noaa.gov/stormevents/)
* **Disaster Declarations:** FEMA Disaster Declarations Summaries. [Source Link](https://www.fema.gov/openfema-data-page/disaster-declarations-summaries-v2)
* **Temperature Data:** NOAA Land & Ocean Temperature Percentiles (2025).

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#fema_chart', 'https://dhur3.github.io/assets/json/fema_disasters.json');
  vegaEmbed('#state_chart', 'https://dhur3.github.io/assets/json/state_storms.json');
</script>
