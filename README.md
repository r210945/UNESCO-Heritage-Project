# Heritage Treasures 🏛️
### An In-Depth Analysis of UNESCO World Heritage Sites in Tableau

Heritage Treasures is a data visualization project built on the UNESCO World Heritage Sites (2019) dataset. It combines country-level distribution, danger/risk status, and regional inscription trends into a single interactive Tableau dashboard and guided story, published to Tableau Server/Public and embedded into a Flask web application for easy stakeholder access.

---

## 📌 Project Overview

Heritage conservation analysts, government policy makers, tourism boards, and cultural researchers need a fast way to see:

- Which countries hold the most UNESCO World Heritage Sites
- Which sites are listed as **In Danger**
- How heritage site inscriptions have trended over time, by region

Instead of manually filtering a large, unstructured spreadsheet, this project delivers all three views in one interactive, filterable dashboard plus a narrated story.

## ✨ Features

| Scenario | Visualization | Key Columns Used |
|---|---|---|
| Heritage Sites by Country | Treemap sized by number of sites | `Country`, `Name_en` |
| Heritage Sites at Risk | Pie chart — In Danger vs Not in Danger | `Danger`, `Name_en` |
| Regional Inscription Trends | Line chart of inscriptions over time, by region | `Date_inscribed`, `Region` |

Additional features:
- 🔍 Interactive filters — Region, Category, Year range
- 📊 Cross-filtering between all three visualizations
- 📖 Multi-scene guided story (Overview → At-Risk Sites → Regional Trends → Takeaways)
- 🌐 Dashboard and story embedded in a Flask web app for public access

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Visualization | Tableau Desktop / Tableau Server / Tableau Public |
| Data Cleaning | Python, Pandas |
| Web App | Flask (Python), Jinja templates, HTML/CSS, Bootstrap |
| Data Source | UNESCO World Heritage Sites (2019) dataset — CSV |
| Hosting | Tableau Server/Public (workbook), Flask app (local or cloud, e.g. Render/Heroku) |

## 📂 Repository Structure
