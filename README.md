# 🏈 NFL Sports Betting Analytics  
A full end-to-end analytics project exploring NFL team performance, betting trends, and long-term outcomes using **Python, SQL (SQLite), and Power BI**.

---

## 📁 Project Structure

NFL-Sports-Betting-Analytics/
│
├── data/
│ ├── processed/
│ │ ├── nfl_betting.db
│ │ ├── nfl_sports_betting_final.csv
│ │ ├── nfl_teams_cleaned.csv
│ │ └── spreadspoke_scores_cleaned.csv
│ └── raw/
│ ├── nfl_teams.csv
│ └── spreadspoke_scores.csv
│
├── notebooks/
│ ├── 01_exploratory_analysis.ipynb
│ └── 02_sql_analysis.ipynb
│
├── powerbi/
│ ├── figures/
│ │ ├── page1_overview.png
│ │ ├── page2_team_performance.png
│ │ ├── page3_betting_insights.png
│ │ └── page4_advanced_analysis.png
│ └── nfl_sports_betting_powerbi.pbix
│
├── reports/
│ └── nfl_betting_analysis.md
│
├── LICENSE
└── README.md


---

# 📊 Project Overview

This project analyzes **11,700+ NFL games** across multiple decades to uncover insights into:

- Team performance trends  
- Home vs away advantages  
- Spread behavior  
- Over/under patterns  
- Stadium & geographic win-rate differences  
- Historical betting edges  

The workflow includes:

### ✔️ **Python (Pandas + NumPy)**
- Cleaning, merging, and preparing raw datasets  
- Creating engineered features (e.g., spread favorite, cover rate, over hits)

### ✔️ **SQL (SQLite)**
Performed inside `02_sql_analysis.ipynb`  
- Aggregate analysis  
- Favorite vs Underdog trends  
- Over/Under performance  
- Team-by-team breakdowns  
- Season-level KPIs

### ✔️ **Power BI**
An interactive 4-page dashboard to visualize long-term patterns and betting trends.

---

# 🧹 1. Data Cleaning & Preparation (Python)

Performed inside `01_exploratory_analysis.ipynb`:

- Cleaned raw datasets  
- Standardized team names  
- Created margin of victory, spread results, and hit-rate metrics  
- Loaded cleaned data into `nfl_betting.db`  

---

# 🛢️ 2. SQL Analysis (SQLite)

All SQL queries run in `02_sql_analysis.ipynb`.

Examples include:

### **Total Games Per Season**
```sql
SELECT schedule_season, COUNT(*) AS total_games
FROM nfl_sports_betting_final
GROUP BY schedule_season
ORDER BY schedule_season;
```
### **Favorite vs Underdog Win Rates**
```sql
SELECT 
    AVG(favorite_covered) AS favorite_cover_rate,
    AVG(1 - favorite_covered) AS underdog_cover_rate
FROM nfl_sports_betting_final;
```
### **Over Hit Rate**
```sql
Copy
SELECT AVG(over_hit) AS over_hit_rate
FROM nfl_sports_betting_final;
```
More analysis includes:

Home vs Away performance

Margin of victory distribution

Stadium-level win rates

Team historical summaries

### 📊 3. Power BI Dashboards (4 Pages)

#### 📌 Page 1 — League Overview  
![League Overview](powerbi/figures/page1_overview.png)

#### 📌 Page 2 — Team Performance  
![Team Performance](powerbi/figures/page2_team_performance.png)

#### 📌 Page 3 — Betting Insights  
![Betting Insights](powerbi/figures/page3_betting_insights.png)

#### 📌 Page 4 — Advanced Analysis  
![Advanced Analysis](powerbi/figures/page4_advanced_analysis.png)
🧠 Key Insights
🔹 Home Teams Win 57% of the time
🔹 Favorites cover only 42% of spreads
🔹 Underdogs cover 57% of the time
🔹 Over hits ~48% of games — slight Under edge
🔹 Teams like the Packers, Cowboys, & 49ers have elite long-term performance
🔹 Stadium and travel distance influence win rates
🚀 Tools Used
Category	Tools
Data Cleaning	Python, Pandas, NumPy
Database	SQLite
Analysis	SQL
Visualization	Power BI
Version Control	Git & GitHub

📝 Future Improvements
Add machine learning prediction model (spread & totals)

Incorporate live betting line movement data

Build an API-driven automated dashboard refresh

Create a forecasting model for game totals


📞Jaylund Harris
Data Analyst | Sports Analytics | Python | SQL | Power BI
Email: jaylundharris@gmail.com
Github: https://github.com/Jaylundharris
Linkedin: https://www.linkedin.com/in/jaylund-harris-571936384/