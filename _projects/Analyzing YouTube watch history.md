---
title: "Analyzing YouTube watch history"
layout: project
permalink: projects/youtube-watch-history-analysis/
programming-language: Python
rating: 4/5
size: medium
start-date: 2025-05
project-type: personal
collaboration-type: solo
tags: 
- personal-project
- solo-project
- data-analysis
- data-visualization
- programming
---  

This project analyzes your YouTube watch history using data from your Google Takeout export.
It is divided into two sections:

1. **Basic Analysis (No API)** — using only the raw JSON data
2. **Extended Analysis (with YouTube API)** — enriched with additional video metadata (e.g., duration, category, tags)

---

## Section One: JSON-Only Analysis

The script processes your watch history and **filters out**:

* **Shorts** and other short-form content
* **Ads**
* **Videos watched within 1 minute** of each other (to reduce noise)
* **Deleted** or **private** videos
* **Music-related content** (based on keywords in channel names)
* Videos with only **hashtags or URLs**

After filtering, the data is converted into a `pandas` DataFrame with the following columns:

* `title`
* `channel`
* `datetime`
* `video_id`

### Outputs & Visualizations

* 📌 Total and unique video counts
* 🔁 Most frequently rewatched videos
* ☁️ Word cloud based on video titles
* 🗓️ Videos watched per **year**, **quarter**, and **month**
* ⏰ Viewing patterns by **hour**, **weekday**, and **month**
* 📺 Top channels overall and per quarter
* 🧠 AI-generated insights into your viewing habits
* 🎯 Personalized video suggestions for future learning

---

## Section Two: API-Enhanced Metadata (WIP)

This part will use the **YouTube Data API** to fetch:

* Video duration
* Category
* Tags
* Region-specific metadata

Currently a work in progress.




[GitHub repo](https://github.com/duster3000/youtube_history_analysis_python)