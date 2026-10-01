# 🏦 Bank of America Financial Analysis

### Historical Stock Prices · Trading Volume · Exploratory Data Analysis

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat-square)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat-square&logo=jupyter&logoColor=white)

An internship project exploring Bank of America’s historical stock
prices and trading activity through data cleaning, statistical
summaries and visual analysis.

👤 **Author:** Preyash Gandhi  
💼 **Internship Role:** Junior Data Analyst – Banking & Financial Services  
📌 **Current Stage:** Week 1 — Data Acquisition, Cleaning and EDA

---

## 🎯 Project Objective

Prepare a public financial dataset, assess its quality and explore
historical patterns in stock prices and trading volume. The Week 1
analysis provides a documented foundation for subsequent forecasting
and risk analysis.

## 📊 Dataset Overview

| Attribute | Details |
|:---|:---|
| Company | Bank of America Corporation |
| Stock ticker | BAC |
| Source | Kaggle |
| Period | 21 February 1973 – 31 December 2025 |
| Records | 13,329 |
| Original columns | 8 |
| Prepared dataset columns | 11 |
| Frequency | Daily trading records |

🔗 **[View the dataset on Kaggle](https://www.kaggle.com/datasets/isaaclopgu/bank-of-america-corp-stock-data-daily-updated)**

### Original Fields

| Column | Description |
|:---|:---|
| `Date` | Date of the trading record |
| `Open` | Opening stock price |
| `High` | Highest stock price during the day |
| `Low` | Lowest stock price during the day |
| `Close` | Closing stock price |
| `Volume` | Number of shares traded |
| `ticker` | Stock symbol |
| `name` | Company and dataset description |

---

## 🧹 Data Cleaning and Preparation

| Check or Step | Result |
|:---|:---|
| Missing values | None found |
| Duplicate rows | None found |
| Duplicate dates | None found |
| Date processing | Converted to datetime with America/New_York timezone |
| Record order | Sorted chronologically |
| Zero-volume records | 6 flagged and retained |
| Closing-price outliers | 66 flagged and retained |
| Final row count | All 13,329 records retained |

Three columns were added:

- 📅 `Year` — supports annual summaries.
- 🚩 `Zero_Volume_Flag` — identifies records with zero trading volume.
- 🔎 `Close_Outlier_Flag` — identifies closing prices outside the
  full-history 1.5 × IQR boundaries.

The causes of zero-volume records were not confirmed. Price outliers
were retained because statistical unusualness alone does not establish
a data error.

---

## 📈 Summary Statistics

| Statistic | Closing Price | Volume (Shares) |
|:---|---:|---:|
| Count | 13,329 | 13,329 |
| Mean | 12.86 | 38,717,124.16 |
| Standard deviation | 12.28 | 76,606,483.08 |
| Minimum | 0.27 | 0 |
| 25th percentile | 1.77 | 489,600 |
| Median | 10.10 | 7,504,200 |
| 75th percentile | 21.21 | 46,978,800 |
| Maximum | 56.25 | 1,226,791,300 |

*Values are rounded where applicable. These statistics summarize the
full historical period; the standard deviation of price levels is
not daily return volatility.*

---

## 🖼️ Visual Analysis

### 1️⃣ Historical Closing Price Trend

![Historical closing price trend](01_Closing_Price_Trend.png)

- The chart tracks closing prices across the dataset’s historical period.
- The lowest recorded closing price was approximately **0.27** on
  **20 December 1974**.
- The highest was **56.25** on **24 December 2025**.

### 2️⃣ Annual Average Closing Price

![Annual average closing price from 2016 to 2025](02_Annual_Average_Close.png)

- Annual average closing price rose from **12.49 in 2016** to
  **25.20 in 2019**, before declining in 2020.
- Following an increase in 2021, annual averages declined in 2022 and 2023.
- **2025 recorded the highest annual average of 46.61** within the
  displayed ten-year period.

*Each bar represents an annual average price, not an annual return.*

### 3️⃣ Daily Trading Volume

![Daily trading volume in millions of shares](03_Daily_Trading_Volume.png)

- Prominent trading-volume spikes appear around **2008–2010**.
- All five highest-volume trading days occurred in **2009**.
- The maximum daily volume was approximately **1,226.79 million shares**
  on **4 December 2009**.

| Date | Volume (Shares) |
|:---|---:|
| 4 December 2009 | 1,226,791,300 |
| 20 May 2009 | 1,197,984,500 |
| 9 April 2009 | 1,029,694,600 |
| 7 May 2009 | 946,806,700 |
| 6 May 2009 | 924,590,100 |

*Volume measures trading activity. It does not by itself reveal the
direction of price movement or establish the causes of a spike.*

### 4️⃣ Closing Price Distribution

![Closing price histogram](04_Closing_Price_Distribution.png)

- The histogram groups closing prices into **30 intervals**.
- More observations occur in lower price ranges, with a long tail
  toward higher prices.
- The distribution is **right-skewed**, consistent with the
  **mean of 12.86** exceeding the **median of 10.10**.

*This chart combines observations from 1973–2025 and does not represent
future price probabilities.*

### 5️⃣ Closing Price Outliers

![Closing price box plot](05_Closing_Price_Box_Plot.png)

- The middle 50% of closing prices lie approximately between
  **1.77 and 21.21**.
- The IQR boundaries were approximately **−27.40 and 50.38**.
- **66 records** exceeded the upper boundary, all from **2025**.
- These observations were flagged and retained.

*The negative lower boundary is a statistical threshold, not an
observed negative stock price.*

---

## 💡 Key Findings

✅ No missing values, duplicate rows or duplicate dates were detected.  
✅ Six zero-volume observations were flagged for transparency.  
✅ The full-history closing-price distribution was right-skewed.  
✅ All five highest-volume trading days occurred in 2009.  
✅ All 66 IQR closing-price outliers occurred in 2025.  
✅ All original records were preserved for subsequent analysis.

---

## 📂 Project Files

| File | Purpose |
|:---|:---|
| [📓 Week1_EDA.ipynb](Week1_EDA.ipynb) | Python notebook with analysis and outputs |
| [📄 Week1_EDA_Report.docx](Week1_EDA_Report.docx) | Detailed Week 1 report |
| [📥 Original dataset](Bank_of_America_historical_data.csv) | Downloaded historical records |
| [🧹 Prepared dataset](Bank_of_America_Cleaned.csv) | Data with year and flag columns |
| [📈 Price trend](01_Closing_Price_Trend.png) | Historical closing-price chart |
| [📊 Annual averages](02_Annual_Average_Close.png) | Annual average closing-price chart |
| [📉 Trading volume](03_Daily_Trading_Volume.png) | Daily trading-volume chart |
| [📊 Price distribution](04_Closing_Price_Distribution.png) | Closing-price histogram |
| [🔎 Outlier analysis](05_Closing_Price_Box_Plot.png) | Closing-price box plot |

---

## ⚙️ Run the Notebook

1. Clone or download this repository.
2. Install the required packages:

       pip install pandas matplotlib jupyter

3. Open `Week1_EDA.ipynb` in Jupyter or VS Code.
4. Keep `Bank_of_America_historical_data.csv` in the notebook’s
   working folder.
5. Select the Python kernel and run the cells from top to bottom.

The notebook exports the prepared CSV and five chart images.
Running it again overwrites exports with the same filenames.

---

## 📝 Limitations

- The analysis covers one company and cannot represent the entire
  banking sector.
- The downloaded file ends on **31 December 2025** and contains no
  2026 trading records.
- Price adjustments for stock splits and dividends remain unconfirmed,
  limiting investment-return interpretation.
- The causes of zero-volume records and volume spikes were not verified.
- Full-history summaries combine different market periods.
- Historical observations do not establish causes or predict future
  performance.

---

## 🚀 Next Stage

- Define a forecasting target and time horizon.
- Split observations chronologically into training and test sets.
- Compare forecasts against a simple baseline.
- Verify price-adjustment details before interpreting investment returns.

---

## 👤 Author

**Preyash Gandhi**

🔗 [GitHub Profile](https://github.com/preyashgandhi00-stack)
