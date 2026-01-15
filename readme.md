# 📱 Smartphones Cleaned Dataset

> An end-to-end data collection, cleaning, and feature engineering project on Indian smartphone specifications.

[![License: CC0](https://img.shields.io/badge/License-CC0-blue.svg)](LICENSE)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Kaggle](https://img.shields.io/badge/Kaggle-Dataset-20BEFF?logo=kaggle)](https://www.kaggle.com/datasets/githubmasterin/smartphones-cleaned-dataset)

---

## 🎯 Project Overview

This repository contains the **complete workflow** for building a clean, structured, and analysis-ready smartphone dataset for the Indian market. Starting from raw scraped HTML, the project demonstrates real-world data engineering skills through systematic cleaning, validation, and feature engineering.

### Key Achievements
- 🔄 Scraped **1,007 phone listings** from Smartprix.com
- 🧹 Cleaned and filtered to **758 high-quality smartphone entries**
- 🛠️ Engineered **29 structured features** from 11 raw text columns
- ✅ Removed 249 feature phones using validation rules
- 📊 Ready for ML modeling and data analysis

---

## ✨ Features

- **Web Scraping**: Selenium-based automation with infinite scroll handling
- **Data Extraction**: BeautifulSoup parsing with custom CSS selectors
- **Data Cleaning**: 200+ lines of systematic cleaning logic
- **Feature Engineering**: Regex-based extraction of numeric values from text
- **Data Validation**: Business rules for quality assurance
- **EDA**: Interactive Plotly visualizations
- **ML-Ready**: Structured dataset for predictive modeling

---

## 📂 Repository Structure

```
smartphones-dataset/
├── LICENSE
├── readme.md
├── requirements.txt
│
├── data/
│   ├── raw/
│   │   └── smartphones.csv          # 1007 extracted phones
│   └── processed/
│       └── smartphones_cleaned.csv  # 758 cleaned phones
│
├── images/                           # Visualizations & assets
│
├── notebooks/
│   ├── 01_extract_phones.ipynb      # HTML → CSV extraction
│   ├── 02_cleaning.ipynb            # Data cleaning & feature engineering
│   └── 03_eda_preview.ipynb         # Exploratory data analysis
│
├── scraped/
│   └── smartprix_phones.html        # Raw scraped HTML
│
└── scripts/
    └── scrape.py                     # Selenium-based scraper
```

---

## 🔄 Data Pipeline

### 1️⃣ Data Collection → `scripts/scrape.py`
```python
# Selenium automation for dynamic content
- Infinite scroll automation
- Load all phone listings
- Save HTML for reproducibility
```
**Output**: `scraped/smartprix_phones.html`

### 2️⃣ Data Extraction → `01_extract_phones.ipynb`
```python
# BeautifulSoup parsing
- Extract 1,007 phone entries
- 11 raw features extracted
- Handle missing values
```
**Output**: `data/raw/smartphones.csv` (1007 rows)

### 3️⃣ Data Cleaning → `02_cleaning.ipynb`
```python
# Systematic cleaning & validation
- Remove 249 feature phones
- Standardize brand names
- Clean price formatting
- Validate specifications
```
**Output**: `data/processed/smartphones_cleaned.csv` (758 rows)

### 4️⃣ Feature Engineering → `02_cleaning.ipynb`
```python
# Text → Structured data
- Split processor specs (brand, name, cores, speed)
- Extract camera details (count, megapixels)
- Parse display resolution (width, height, refresh rate)
- Create connectivity flags (5G, VoLTE, NFC)
- Extract charging specs (battery, wattage)
```
**Output**: 29 engineered features

### 5️⃣ Exploratory Analysis → `03_eda_preview.ipynb`
```python
# Interactive visualizations
- Price distribution analysis
- Brand positioning
- Feature correlations
- Hardware trends
```

---

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- Chrome WebDriver (for scraping)

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/abhinavflac/smartphones-dataset.git
cd smartphones-dataset
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Run the notebooks**
```bash
jupyter notebook notebooks/
```

### Usage

**Option 1: Use the cleaned dataset directly**
```python
import pandas as pd

# Load cleaned data
df = pd.read_csv('data/processed/smartphones_cleaned.csv')
print(df.shape)  # (758, 29)
```

**Option 2: Run the complete pipeline**
```bash
# Step 1: Scrape data (optional - HTML already provided)
python scripts/scrape.py

# Step 2: Extract phones
# Open notebooks/01_extract_phones.ipynb

# Step 3: Clean & engineer features
# Open notebooks/02_cleaning.ipynb

# Step 4: Exploratory analysis
# Open notebooks/03_eda_preview.ipynb
```

---

## 📊 Dataset Details

### Statistics
- **758 smartphones** (feature phones excluded)
- **29 engineered features**
- **35+ brands** (Samsung, Xiaomi, Realme, OnePlus, etc.)
- **Price range**: ₹5,000 - ₹150,000+

### Feature Schema

| Category | Features | Description |
|----------|----------|-------------|
| **Basic** | `brand`, `model`, `price_inr`, `rating_score` | Brand, model name, price, user rating |
| **Processor** | `processor_brand`, `processor_name`, `core_count`, `clock_speed_ghz` | CPU specifications |
| **Memory** | `ram_gb`, `storage_gb` | RAM and internal storage |
| **Display** | `display_inches`, `res_width_px`, `res_height_px`, `refresh_rate_hz` | Screen specifications |
| **Battery** | `battery_mah`, `charging_watt`, `fast_charging` | Battery capacity and charging |
| **Camera** | `rear_camera_count`, `front_camera_count`, `rear_camera_main_mp`, `front_camera_main_mp` | Camera configuration |
| **Connectivity** | `has_5g`, `has_vo5g`, `has_volte`, `has_nfc`, `has_ir_blaster` | Network and connectivity |
| **Software** | `os_name` | Operating system |
| **Storage** | `memory_card_supported`, `memory_card_type` | External storage support |

### Data Quality Improvements
✅ Removed 249 feature phones and invalid entries  
✅ Standardized brand names across 35+ brands  
✅ Extracted numeric values from text descriptions  
✅ Created boolean flags for categorical features  
✅ Validated processor brands (Snapdragon, Dimensity, Helio, Unisoc, etc.)  
✅ Parsed complex camera configurations (e.g., "50 MP + 8 MP + 2 MP")  
✅ Split display resolutions (e.g., "1080 x 2400 pixels")  

### Validation Rules Applied
- **Minimum battery**: 3000 mAh
- **Minimum display**: > 2.8 inches
- **Minimum RAM**: > 32 MB
- **Valid processor** required
- **Modern OS**: Android 4.0+ or iOS

---

## 🛠️ Tech Stack

### Core Technologies
- **Python 3.8+** - Programming language
- **Jupyter Notebook** - Interactive development
- **Selenium** - Web scraping automation
- **BeautifulSoup4** - HTML parsing
- **Pandas** - Data manipulation
- **NumPy** - Numerical operations
- **Matplotlib & Seaborn** - Data visualization
- **Plotly** - Interactive charts

### Dependencies
```txt
pandas
numpy
beautifulsoup4
requests
selenium
matplotlib
seaborn
```

---

## 💡 Use Cases

### Machine Learning
- 🤖 Price prediction models (regression)
- 📈 Feature importance analysis
- 🎯 Brand clustering and segmentation
- 💰 Value-for-money recommendation systems

### Data Analysis
- 📊 Market trend analysis
- 🔍 Hardware specification evolution
- 💵 Pricing strategy insights
- 📱 Camera and battery capacity trends

### Portfolio Projects
- 📈 EDA dashboards (Streamlit, Plotly Dash)
- 🌐 Web applications for price prediction
- 📚 Teaching data cleaning workflows
- 🎓 Practice dataset for data science beginners

---

## 🧠 Technical Highlights

This project demonstrates:

### Data Engineering Skills
✅ **Web Scraping** - Selenium automation with infinite scroll  
✅ **HTML Parsing** - BeautifulSoup with CSS selectors  
✅ **Data Cleaning** - 200+ lines of cleaning logic  
✅ **Regex Mastery** - Complex pattern extraction  
✅ **Feature Engineering** - Text to structured data transformation  
✅ **Data Validation** - Business rule implementation  
✅ **ETL Pipeline** - End-to-end reproducible workflow  

### Data Science Best Practices
✅ Reproducible pipeline with clear documentation  
✅ Raw data preservation (never modify source)  
✅ Systematic missing value handling  
✅ Outlier detection with domain justification  
✅ Feature engineering guided by domain knowledge  
✅ Data quality validation at each stage  

> **Note**: This project emphasizes that **80% of data science work** is about understanding and preparing data correctly, not just building models.

---

## 📦 Kaggle Dataset

The cleaned dataset is also available on Kaggle:

👉 **[Smartphones Cleaned Dataset (India, 2025)](https://www.kaggle.com/datasets/githubmasterin/smartphones-cleaned-dataset)**

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

### Possible Enhancements
- [ ] Add more brands (international markets)
- [ ] Include GPU specifications
- [ ] Add camera sensor details (Sony IMX, Samsung ISOCELL)
- [ ] Expand connectivity features (WiFi 6, Bluetooth versions)
- [ ] Include launch dates for trend analysis
- [ ] Add weight and dimensions
- [ ] Include warranty information

Feel free to open an issue or submit a pull request.

---

## 📜 License

This project is licensed under **CC0 (Public Domain)**.  
You are free to use, modify, and distribute the data and code without restriction.

---

## 📧 Contact

- **Kaggle**: [@abhinavflac](https://www.kaggle.com/githubmasterin)
- **Dataset**: [Smartphones Cleaned Dataset](https://www.kaggle.com/datasets/githubmasterin/smartphones-cleaned-dataset)

For questions or collaboration, feel free to open an issue!

---

## ⭐ Show Your Support

If this project helped you or you found it useful, please consider giving it a star!
