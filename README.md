# 📉 Quantitative Market Risk Analysis (VaR & ES)

[cite_start]**Project:** Quantitative Market Risk Measures / Ilościowe Miary Ryzyka Rynkowego [cite: 225]  
[cite_start]**Author:** Wiktor Suchoński-Romaniuk [cite: 226]  
**Language:** R (R Markdown)

---

## 📋 Project Overview

[cite_start]This project provides a comprehensive analysis of market risk for **Fast Retailing Co.** (owner of Uniqlo), based on daily stock data from **November 2017 to November 2025**[cite: 228, 229].

[cite_start]The primary goal is to estimate potential financial losses using **Value at Risk (VaR)** and **Expected Shortfall (ES)** metrics, and to compare the efficacy of different statistical models in capturing market volatility, particularly during the COVID-19 crash[cite: 278, 314].

## 🚀 Key Features & Methodology

The analysis is structured into three main stages:

### 1. Data Processing & Statistical Analysis
* [cite_start]Analysis of daily closing prices and calculation of **Logarithmic Returns** to normalize volatility[cite: 252].
* [cite_start]Identification of statistical properties (skewness, kurtosis) which revealed "fat tails" (kurtosis > 4), indicating a higher probability of extreme events than a normal distribution suggests[cite: 273, 274].

### 2. Risk Modelling (VaR & ES)
[cite_start]Implementation of two distinct approaches to estimate risk at a 99% confidence level[cite: 278]:
* **Historical Simulation:** Standard approach using a rolling window of 250 days.
* [cite_start]**Weighted Historical Simulation:** Applies exponential weights to give more significance to recent observations, allowing the model to adapt faster to changing market conditions[cite: 316, 401].

### 3. Backtesting (Model Validation)
[cite_start]Rigorous validation of the models using statistical tests[cite: 320]:
* **Kupiec Test:** Checks if the frequency of exceptions (losses exceeding VaR) matches the expected confidence level.
* [cite_start]**Christoffersen Test:** Checks for the *independence* of exceptions (to ensure the model doesn't fail in clusters)[cite: 420].

---

## 📊 Key Findings

* [cite_start]**Impact of COVID-19:** The analysis highlighted the extreme volatility in March 2020, where daily fluctuations exceeded 14%[cite: 424].
* [cite_start]**The "Ghost Effect":** The standard Historical Method suffered from a "ghost effect"—after the initial shock, it remained overly conservative for 250 days, artificially inflating risk estimates long after the market stabilized[cite: 314, 400].
* **Superiority of Weighted Method:** The Weighted Historical Method proved to be more agile. [cite_start]It "forgot" the old shocks faster and adjusted to the current market volatility, resulting in better backtesting scores[cite: 398, 401].

---

## 🛠️ Technologies & Libraries

The project is written in **R** and utilizes the following libraries for data manipulation, calculation, and visualization:

* [cite_start]`ggplot2` - For visualizing stock prices, returns, and risk metrics[cite: 231].
* `dplyr` - For data manipulation and transformation.
* [cite_start]`psych` - For generating descriptive statistics[cite: 231].
* [cite_start]`kableExtra` - For formatting professional data tables[cite: 243].
* `zoo` - For rolling window calculations.

---

## 📥 How to Run

1.  Clone the repository.
2.  Ensure you have R and RStudio installed.
3.  Install required packages:
    ```r
    install.packages(c("ggplot2", "dplyr", "psych", "kableExtra", "zoo", "lubridate"))
    ```
4.  Open `IMRR_Projekt_WSR.Rmd` and knit the document to PDF or HTML to see the full analysis and charts.

---
© 2025 Wiktor Suchoński-Romaniuk
