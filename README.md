# 📈 VN30 Market Volatility Analysis using Principal Component Analysis (PCA)

## 📌 Project Overview
This project applies **Principal Component Analysis (PCA)** to the top 30 largest capitalized companies in the Vietnam stock market (VN30). By reducing the dimensionality of stock returns, the analysis identifies the primary underlying "market factor" driving the volatility of the VN30 index. 

## 💼 Business Context
In financial markets, stock prices often move together due to systemic macroeconomic factors. For portfolio managers, quantitative analysts, and investors, understanding these hidden market drivers is crucial for:
- **Risk Management:** Quantifying systemic risk vs. idiosyncratic risk.
- **Portfolio Diversification:** Identifying the true underlying correlations between assets.
- **Algorithmic Trading:** Developing statistical arbitrage or factor-based trading models.

## 🎯 Objective
- Extract the principal components of the VN30 stock returns.
- Evaluate the explanatory power of the First Principal Component (PC1).
- Analyze the relationship between PC1 and the actual VN30-Index to validate if PC1 acts as a proxy for the broader market.

## 📊 Dataset Description
- **VN30 Stocks Data:** Daily closing prices of the 30 constituent stocks of the VN30 index.
- **VN30-Index Data:** Daily closing levels of the VN30 benchmark index.
- **Timeframe:** April 01, 2025 – April 01, 2026.
- **Data Sources:** `yfinance` API (stocks) & Investing.com (index).

## 🛠 Methodology
1. **Data Engineering:** Data merging, timezone synchronization, and missing value treatment.
2. **Feature Engineering:** Calculation of Daily Simple Returns.
3. **Data Standardization:** Z-score normalization (mean = 0, std = 1) to prevent high-volatility stocks from skewing the PCA.
4. **Statistical Modeling (PCA):**
   - Covariance Matrix computation.
   - Eigenvalues & Eigenvectors extraction.
   - Variance Explained & Cumulative Variance calculations.
5. **Evaluation & Visualization:** Scree plots and time-series comparison between standardized PC1 and the VN30-Index.

## 💡 Key Insights
- **Strong Market Factor:** A significant portion of the VN30's total variance can be explained by just the first few principal components.
- **PC1 as the Market Proxy:** The First Principal Component (PC1) highly correlates with the actual VN30-Index. This mathematically proves that the Vietnamese large-cap market is heavily driven by a single systemic market factor, demonstrating high co-movement among top equities.

## 💻 Technologies Used
- **Language:** Python
- **Libraries:** `pandas`, `numpy`, `yfinance`, `matplotlib`
- **Environment:** Jupyter Notebook / Google Colab

## 🚀 How to Run the Project
1. Clone this repository:
   ```bash
   git clone https://github.com/SonnyDuck/PCA-VN30_Analysis.git
   ```
2. Navigate to the project directory:
   ```bash
   cd PCA-VN30_Analysis
   ```
3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Run the Jupyter Notebook:
   ```bash
   jupyter notebook notebooks/PCA_VN30_Analysis.ipynb
   ```

## 🔮 Future Improvements
- **Sector Rotation Analysis:** Grouping PCA loadings by GICS sectors (e.g., Banking, Real Estate) to identify sector-specific impacts.
- **Predictive Modeling:** Using the extracted Principal Components as features for Machine Learning models to predict future index movements.
- **Interactive Dashboard:** Building a Streamlit or Power BI dashboard to dynamically visualize the PCA weights and rolling correlations.
