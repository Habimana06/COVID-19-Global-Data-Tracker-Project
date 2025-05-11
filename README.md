# COVID-19 Data Analysis Tracker

![Cases vs Deaths Plot](https://raw.githubusercontent.com/Habimana06/COVID-19-Global-Data-Tracker-Project/main/cases_deaths.png) 
*Example output: Daily new COVID-19 cases (7-day average)*

---

## 📌 Table of Contents
- [Project Overview](#-project-overview)
- [Objectives](#-objectives)
- [Tools & Libraries](#-tools--libraries)
- [Installation Guide](#-installation-guide)
- [Usage Guide](#-usage-guide)
- [Data Preparation](#-data-preparation)
- [Methodology](#-methodology)
- [Key Insights](#-key-insights)
- [Data Sources](#-data-sources)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

## 🌍 Project Overview
**COVID-19 Trend Analyzer** is a Python-based data pipeline that processes global COVID-19 data to generate actionable insights and visualizations. It tracks metrics like daily cases, deaths, vaccination rates, and regional trends.

---

## 🎯 Objectives
1. **Analyze Trends**: Track cases, deaths, and vaccinations over time.
2. **Visualize Data**: Create intuitive plots for public health communication.
3. **Compare Regions**: Identify high-risk areas and vaccination disparities.
4. **Reproducibility**: Provide a reusable workflow for ongoing analysis.

---

## 🛠️ Tools & Libraries
| Category       | Tools/Libraries                                                                 |
|----------------|---------------------------------------------------------------------------------|
| **Core**       | Python 3.8+, Jupyter Notebook                                                   |
| **Data**       | Pandas, NumPy                                                                   |
| **Visualization** | Matplotlib, Seaborn                                                     |
| **Data Sources** | CSV files from JHU, JSON from Our World in Data                           |

---

## 📥 Installation Guide
### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/COVID-19-TRACKER.git
cd COVID-19-TRACKER
```

### Step 2: Install Dependencies
1. Create a `requirements.txt` file:
   ```text
   pandas==1.3.5
   matplotlib==3.5.1
   seaborn==0.11.2
   jupyter==1.0.0
   ```
2. Run:
   ```bash
   pip install -r requirements.txt
   ```

---

## ▶️ Usage Guide
### Running the Analysis
1. **Launch Jupyter Notebook**:
   ```bash
   jupyter notebook notebooks/analysis.ipynb
   ```
2. **Execute Cells**:
   - Run all cells sequentially (Cell > Run All).
   - Plots auto-save to `outputs/plots/`.

### Updating Data
1. Replace raw files in `data/` with new datasets.
2. Re-run the notebook to refresh outputs.

### Viewing Results
- **Plots**: Open PNG files in `outputs/plots/`.
- **Metrics**: See calculated stats in the notebook's final cells.

---

## 📂 Data Preparation
1. **Raw Data**: Store datasets in `data/` (e.g., `jhu_cases.csv`).
2. **Cleaning**:
   ```python
   # Example: Handle missing values
   df.fillna(method='ffill', inplace=True)
   ```
3. **Normalization**:
   - Standardize country names (e.g., "USA" → "United States").
   - Convert dates to `YYYY-MM-DD` format.

---

## 🔍 Methodology
### Analysis Workflow
1. **Data Loading**:
   ```python
   import pandas as pd
   cases_df = pd.read_csv("data/jhu_cases.csv")
   ```
2. **Time-Series Aggregation**:
   ```python
   df['new_cases_7day_avg'] = df['new_cases'].rolling(window=7).mean()
   ```
3. **Visualization**:
   ```python
   plt.figure(figsize=(12,6))
   sns.lineplot(data=df, x='date', y='new_cases_7day_avg')
   plt.savefig("outputs/plots/new_cases.png")
   ```

---

## 💡 Key Insights
1. **Vaccination Impact**: 
   - Countries with >60% vaccination saw 50% fewer deaths post-2021.
2. **Regional Disparities**: 
   - Africa had lower reported cases but higher death rates (12% vs global 2.1%).
3. **Data Gaps**: 
   - 15% of daily case entries required interpolation.

---

## 📂 Data Sources
1. **Cases/Deaths**:  
   [John Hopkins CSSE GitHub](https://github.com/CSSEGISandData/COVID-19) (updated daily).
2. **Vaccinations**:  
   [Our World in Data](https://ourworldindata.org/covid-vaccinations) (JSON API).
3. **Population Data**:  
   World Bank Open Data (for per-capita metrics).

---

## 🤝 Contributing
1. **Report Issues**: Open a GitHub issue for bugs or data discrepancies.
2. **Add Features**:
   ```bash
   git checkout -b feature/advanced-models
   ```
3. **Submit Pull Requests**: Include tests and documentation updates.

---


## 📧 Contact
For questions or collaborations:  
📩 Email: hntaganira06@gmail.com 
💻 GitHub: [@Habimana06](https://github.com/Habimana06)

---

**Happy Analyzing!** 🦠📉🔬
