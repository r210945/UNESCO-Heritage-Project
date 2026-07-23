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
## 🧹 Data Preparation

- Removed duplicate and null rows
- Standardized inconsistent `Country` / `Region` names
- Converted `Date_inscribed` to a proper Date field
- Derived calculated fields:
  - **Danger Flag** — boolean flag from the raw danger status
  - **Years Since Inscription** — current year minus `Date_inscribed`
  - **Region Rank** — rank of each region by total site count
  - **Site Count** — aggregate count per country/region

## 🚀 Getting Started

### Prerequisites
- Python 3.x
- Tableau Desktop (for authoring/editing the workbook)
- A Tableau Public or Tableau Server account (for publishing)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/<org>/heritage-treasures.git
cd heritage-treasures

# 2. Install Python dependencies
pip install -r requirements.txt --break-system-packages

# 3. Clean the raw dataset (creates the cleaned CSV used by Tableau)
python scripts/clean_data.py
```

### Configure the Tableau Embed

Set the published dashboard/story URL as an environment variable before running the app:

```bash
export TABLEAU_EMBED_URL="https://public.tableau.com/views/<your-workbook-path>"
```

### Run the App

```bash
python app.py
```

Then open **http://127.0.0.1:5000** in your browser to view the embedded dashboard and story.

## ✅ Testing

Manual User Acceptance Testing covered:
- Chart accuracy (treemap, pie chart, trend line) against raw dataset totals
- Filter cross-interaction across all three visualizations
- Story scene navigation
- Dashboard rendering inside the Flask-embedded page

Result: 6/6 test cases passed, with 2 minor low-severity issues logged (initial embed load delay, story caption overflow on very small screens).

## 📈 Performance Notes

- **Data rendered:** ~1,121 UNESCO World Heritage Site records
- **Filters:** 3 (Region, Category, Year range)
- **Calculated fields:** 4 (Danger Flag, Years Since Inscription, Region Rank, Site Count)
- **Visualizations:** 3 core charts combined into 1 dashboard + a 3-scene story

## 🔭 Future Scope

- Live/incremental data connection instead of a static extract
- Geographic map view plotting sites by latitude/longitude
- A `/api/summary` Flask endpoint for programmatic access to aggregate counts
- Enrich the dataset with visitor numbers or funding data for deeper impact analysis

## 👥 Team

| Name | Role |
|---|---|
| Devendra Reddy | Team Lead |
| Dhara Mahitha | Member |

## 🔗 Links

- **Live Demo:** _[add Tableau Public/Server or Flask app link]_
- **GitHub Repository:** _[add repository link]_
- **Dataset Source:** _[add UNESCO/Kaggle dataset link used]_

## 📄 License

Add your preferred license here (e.g. MIT).
