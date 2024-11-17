# Feature Engineering the NVIDIA Stock  

### **1. Introduction**  
This project aims to perform a comprehensive **Feature Engineering and Exploratory Data Analysis (EDA)** on NVIDIA's stock data. By extracting key features and analyzing their behavior, we gain insights into stock performance, price trends, volatility, and market activity. The dataset is sourced from Yahoo Finance (`yfinance`) for a 1-year period.  

---

### **2. Methodology**  
1. **Data Collection**: Historical stock data for NVIDIA was fetched using the `yfinance` API.  
2. **Data Preparation**:  
   - Reset the index to use `Date` as a column.  
   - Verified and converted `Date` to `datetime` format.  
3. **Feature Engineering**: Derived various stock-related features for analysis.  
4. **Visualization**: Analyzed trends using matplotlib and seaborn.  

---

### **3. EDA and Feature Engineering**  

1. **Daily Returns**: Calculated percentage change in daily closing prices.  
   <br>![Daily Returns Formula](https://quicklatex.com/cache3/b0/ql_e981c0a7550d754c0e6b4d8ccc073db0_l3.png)

2. **Price Change**: Difference in closing prices between consecutive days.  

3. **5-Day Moving Average**: Average closing price over a rolling 5-day window.  

4. **High-Low Spread**: Difference between daily high and low prices.  

5. **Volatility**: Standard deviation of daily returns over a 20-day rolling window.  

6. **10-Day Simple Moving Average (SMA)**: Average closing price over a rolling 10-day window.  

7. **10-Day Exponential Moving Average (EMA)**: Weighted average of closing prices over 10 days, giving more weight to recent days.  

8. **Lagged Features**:  
   - **Lagged Closing Price**: Previous day's closing price.  
   - **Lagged Returns**: Previous day's returns.  

9. **Temporal Features**:  
   - **Day of the Week**: Weekday (0=Monday, ..., 6=Sunday).  
   - **Month**: Month of the year.  
   - **Year**: Extracted from the `Date`.  

10. **Cumulative Returns**: Total compounded return over the period.  
    <br>![Cummulative Returns](https://quicklatex.com/cache3/89/ql_b04f6219206bb22246cf62dbe077cd89_l3.png)

11. **Scaled Volume**: Daily trading volume scaled for visualization (in millions).  

---

### **4. Approach**  

#### **Relevant Plots and Inferences**  

1. **Daily Closing Price with Moving Averages**  
   - **Plot**: Line plot showing daily returns and 5-Day and 10-Day moving averages.  
   - **Inference**: The upward trend in the stock price is evident from the rising moving averages. The 5-day moving average crossing above the 10-day moving average suggests potential bullish momentum.<br> 

   ![Daily Close with Moving Average](https://github.com/1Aditya7/Feature-Engineering-the-Nvidia-Stock/blob/main/nvdaFE/dailyAnd5D10D.png) 

2. **Daily Returns and Volatility**  
   - **Plot**: This plot shows daily percentage returns alongside their rolling volatility. 
   - **Inference**: The plot shows the daily returns and volatility of a stock. The volatility fluctuates over time, with periods of higher and lower volatility. The daily returns exhibit significant variation, with both positive and negative returns. This suggests a volatile stock with potential for both going long and short.<br>

   ![Daily Returns and Volatility](https://github.com/1Aditya7/Feature-Engineering-the-Nvidia-Stock/blob/main/nvdaFE/dailyRetandVol.png) 

3. **Daily Returns and Cummulative Returns**  
   - **Plot**: This visualization combines daily returns with cumulative returns to show the stock's overall growth trajectory. 
   - **Inference**: The plot shows the daily returns and cumulative returns of a stock. The daily returns fluctuate significantly, indicating high volatility. The cumulative returns show an overall upward trend, suggesting positive performance over the period.<br>

   ![Daily Returns and Cummulative Returns](https://github.com/1Aditya7/Feature-Engineering-the-Nvidia-Stock/blob/main/nvdaFE/dailyRetAndCummRet.png)

4. **Moving average and Daily Price Change**  
   - **Plot**: This plot compares the stock's moving average (5-day and 10-day) with daily price changes to reveal how smoothed trends align with short-term price fluctuations.
   - **Inference**: The plot shows the closing price of a stock along with its 5-day and 10-day moving averages and daily price change. The stock price shows an upward trend, with the moving averages confirming the overall direction. The daily price change indicates significant fluctuations, suggesting a high-risk stock.

   ![Moving Average and Price Change](https://github.com/1Aditya7/Feature-Engineering-the-Nvidia-Stock/blob/main/nvdaFE/maAndDailyPriceChange.png)

---

### **5. Results**  

- **Daily Returns**: Highlighted the variability in stock price movements.  
- **Volatility**: Showed periods of high/low market activity.  
- **Moving Averages**: Demonstrated short-term trends and price smoothness.  
- **Temporal Features**: Identified trends based on the day of the week and month.  
- **Cumulative Returns**: Illustrated the growth trajectory of the stock.  
- **Heatmap**: Showed strong correlations between price features (e.g., Adj Close vs Close).  

---

### **6. Limitations and Future Scope**  

#### **Limitations**  
1. Focused only on NVIDIA stock; results may not generalize to other securities.  
2. Temporal scope limited to 1 year.  
3. Does not include macroeconomic factors or market-wide trends.  

#### **Future Scope**  
1. Expand analysis to multiple stocks and perform comparative analysis.  
2. Build predictive models using the engineered features:  
   - Predict future prices using regression models.  
   - Classify price movements using machine learning classifiers.  
3. Integrate sentiment analysis using news data.  
4. Use advanced techniques like GARCH for volatility modeling.  

---

### **7. Conclusions**  

This project successfully performed a detailed feature engineering and EDA on NVIDIA's stock data. The engineered features provide a solid foundation for further analysis and predictive modeling. Insights into stock price trends, volatility, and trading activity are visually captured, offering valuable perspectives for trading strategies.  
