# Bitcoin Risk and Return 🎲

## Introduction
**Bitcoin Risk and Return** is a financial data analysis showcase using Jupyter Notebook, focusing on the cryptocurrency's risk and return dynamics. Bitcoin was chosen for its maturity and widespread popularity.


## Tools Used
- **YFinance:** To gather most of the financial data using the Yahoo Finance API.
- **Jupyter Notebook:** The interactive environment used for coding and data analysis.
- **Pandas:** For cleaning, standardizing, manipulating, and analyzing datasets.
- **Matplotlib and Seaborn:** For creating charts.
- **NumPy and SciPy:** For numerical operations.
- **Statsmodels:** For time series decomposition.


## Analysis Overview
This project presents a brief overview of bitcoin's price evolution, emphasizing key market cycles, trends, and seasonal patterns. The focus then shifts to an in-depth analysis of returns and volatility, comparing the cryptocurrency with other major assets, alongside an evaluation of important risk metrics.
For detailed information about the datasets, check it [here](/data/README.md).


### Table of Contents
- [Bitcoin Price](#BTC_price)
    - [Major Market Cycles](#BTC_cycles)
    - [STL Decomposition](#BTC_decomposition)
- [Bitcoin Returns](#BTC_returns)
    - [Year-over-Year Returns](#BTC_YoY_returns)
    - [Before vs. Since 2014](#BTC_price_2014)
    - [Price vs. Returns](#BTC_price_vs_returns)
- [Bitcoin Volatility](#BTC_vlt)
    - [Yearly Volatility](#BTC_yearly_vlt)
    - [Price vs. Volatility](#BTC_price_vs_vlt)
    - [Volatility vs. Returns](#BTC_vlt_vs_return)
- [Bitcoin Extra Risk Metrics](#BTC_risk_adjusted)
    - [Risk-Adjusted Returns](#BTC_risk_adjusted)
    - [Value at Risk and Expected Shortfall](#BTC_var)

<br> <!-- Line break -->


### Bitcoin Price Over Time ₿ <a name = "BTC_price"></a>
![Bitcoin price chart log](/images/1_BTC_price_log.png)
*Line chart of the historical price of bitcoin, with a logarithmic scale on the y-axis.*

<details>
<summary>Click to reveal non-logarithmic chart</summary>

![Bitcoin price chart](/images/1_BTC_price.png)
*Line chart of the historical price of bitcoin.*
</details>

**Key takeaways:**
- The all-time low occurred at the very beginning of the dataset, with bitcoin trading around 5 cents.
- From there, the price rose rapidly, peaking in mid-2011.
- In 2013, bitcoin gained significant mainstream attention, going viral and breaking its previous all-time high, peaking by the end of the year.
- After three years of relatively low activity, bitcoin went viral again in 2017, reaching nearly $20k.
- The market remained quiet from 2018 to 2020, with minimal performance until bitcoin regained momentum in late 2020, going viral once again.
- Following a sharp collapse in 2022, bitcoin rebounded quickly, reaching a new all-time high of around $72.4k in March 2024.
- Since the first entry, bitcoin's price has skyrocketed by nearly 126,245,855%, meaning its initial value has multiplied by about 1,262,460 times.

<br> <!-- Line break -->


### Major Market Cycles of Bitcoin Over Time 🔄 <a name = "BTC_cycles"></a>
![Bitcoin cycles chart](/images/1_BTC_major_cycles.png)
*Bar charts of the major rallies and crashes of bitcoin.*

**Key takeaways:**
- Bitcoin's price is known for its extreme volatility, often experiencing dramatic surges in value followed by steep declines of up to 80-90%.
- The first bull market saw the most significant price increase, soaring by approximately 58,514% in less than a year. Given the diminishing returns in subsequent rallies, it's unlikely this record will be surpassed.
- The first bear market was equally extreme, with bitcoin losing about 93% of its value in just 163 days.
- The second rally came close to the first in percentage gains, though it took two years to unfold.
- Throughout the years, both bull and bear markets have become less intense, especially the bull phases, reflecting a gradual loss of momentum.
- Although the last surge was weaker compared to previous cycles, it still showed a remarkable gain of approximately 1,980%, achieved over nearly 3 years.

<br> <!-- Line break -->


### STL Decomposition (Trend, Seasonality, and Residuals) 📈 <a name = "BTC_decomposition"></a>
#### Trend Analysis
![Bitcoin trend chart](/images/1_BTC_trend.png)
*Line chart of the trend component of the historical price of bitcoin, with a logarithmic scale on the y-axis.*

**Key takeaways:**
- The trend saw massive growth up until 2014.
- Since then, bitcoin has been rising consistently, although with progressively less momentum.
- Bitcoin's viral surges are clearly visible, with each bounce decreasing in magnitude, indicating increased stability as the years go by.
- Overall, the long-term trend appears to follow a logarithmic growth pattern.

#### Seasonality Analysis
![Bitcoin seasonal chart](/images/1_BTC_seasonal.png)
*Line chart of the average seasonal component of the price of bitcoin throughout the year.*

**Key takeaways:**
- Bitcoin’s average seasonality shows notable changes.
- It typically peaks at the beginning of spring.
- Following this peak, the price generally declines, reaching its lowest point by the end of summer.

*For more details about this section, check the respective [Notebook](/notebooks/1_BTC_price.ipynb).*

<br> <!-- Line break -->


### Bitcoin Returns Over Time 💰 <a name = "BTC_returns"></a>
![Bitcoin returns chart](/images/2_BTC_returns.png)
*Line chart of the historical 90-day and 1-year moving averages of daily returns of bitcoin.*

**Key takeaways:**
- In the early years, up until 2014, bitcoin experienced significant price fluctuations.
- As the asset matured, particularly after 2019, price movements stabilized, indicating a clear trend toward less extreme volatility.
- The highest daily return occurred in July 2010, reaching approximately 72%, while the lowest return was around -39% in June 2011.
- The compound annual growth rate (CAGR) has been roughly 170% to date.

#### Comparison of Returns With Other Assets
![Bitcoin returns comparison chart](/images/2_BTC_returns_comparison.png)
*Line chart comparing the historical 1-year moving average of weekly returns of bitcoin with other major assets.*

**Key takeaways:**
- Bitcoin has outperformed other major assets, with significantly higher average returns, despite experiencing the lowest single-period returns.
- The disparity in returns was particularly striking before 2019, with the cryptocurrency leading by a wide margin.
- On the downside, bitcoin also experienced the steepest negative returns, sometimes close to crude oil and US 10-year bonds.
- So far, bitcoin’s average weekly returns have been more than 10 times greater than those of the S&P 500.

#### Distribution of Returns
![Bitcoin returns distribution chart](/images/2_BTC_returns_dist.png)
*Histogram chart of the distribution of daily returns of bitcoin.*

| Average return | Median return | Standard deviation | Min return | Max return | Skewness | Kurtosis |
| -------------- | ------------- | ------------------ | ---------- | ---------- | -------- | -------- |
| 0.0027         | 0.0014        | 0.0433             | -0.4914    | 0.54       | 0.0093   | 24.9568  |

**Key takeaways:**
- The average return suggests long-term appreciation, while the lower median return indicates the presence of some positive outliers.
- A high standard deviation highlights the significant volatility in bitcoin's returns.
- This asset experiences rare but extreme returns, both positive and negative.
- The skewness, being close to zero, suggests that the distribution of returns is nearly balanced between gains and losses.
- However, the extremely high kurtosis indicates that extreme returns, far beyond what would be expected in a normal distribution, are more frequent.

#### Distribution of Yearly Rolling Returns
![Bitcoin yearly rolling returns distribution chart](/images/2_BTC_returns_y_rol_dist.png)
*Histogram chart of the distribution of yearly rolling returns of bitcoin.*

| Average return | Median return | Standard deviation | Min return | Max return | Skewness | Kurtosis |
| -------------- | ------------- | ------------------ | ---------- | ---------- | -------- | -------- |
| 0.8669         | 0.7962        | 1.2837             | -1.7385    | 5.6282     | 0.7123   | 0.6934   |

**Key takeaways:**
- Shifting from daily to rolling yearly returns leads to a noticeable transformation in the distribution.
- The average return now aligns more closely with the median, indicating that yearly returns have less outliers compared to daily returns.
- A higher standard deviation reflects greater dispersion in yearly returns, highlighting larger fluctuations over time.
- Minimum and maximum returns become more extreme over longer periods, which is expected (note that log returns can fall below -1).
- An increase in positive skew suggests that large positive returns are more common in yearly returns compared to daily ones.
- While still positive, the significantly lower kurtosis shows a reduction in extreme outliers when compared to the daily return distribution.

<br> <!-- Line break -->


### Bitcoin Year-over-Year Returns Over Time 📊 <a name = "BTC_YoY_returns"></a>
![Bitcoin YoY returns chart](/images/2_BTC_YoY_returns.png)
*Bar chart of the historical year-over-year returns of bitcoin, with a symmetrical logarithmic scale on the y-axis.*

**Key takeaways:**
- Over the past 15 years (assuming 2024 will be positive), only 3 years have ended with negative returns.
- Despite a dramatic 93% drop in the second half of 2011, that year still ranks as bitcoin's second best, reflecting the extreme volatility in its early days.
- 2013 was bitcoin's "golden year", with an extraordinary 5,562% rise. It's highly unlikely that this record will ever be surpassed.
- In 2018, the cryptocurrency faced its biggest downturn, losing around 72% of its value.
- Since 2013, bitcoin's standout years have shown diminishing returns, confirming a slowdown in the momentum seen earlier, as the market moves toward more stable price patterns.
- This could be attributed to bitcoin's higher market capitalization and increased liquidity, making it harder for single events or trades to trigger large price movements.
- Another factor may be the rise of ethereum, launched in mid-2015. Its growing popularity, alongside the emergence of other altcoins, has likely diverted attention and capital from bitcoin.

<br> <!-- Line break -->


### Returns Before vs. Since 2014 🍕 <a name = "BTC_price_2014"></a>
![Bitcoin price 2014 chart](/images/2_BTC_price_2014.png)
*Line chart comparing the bitcoin price evolution before vs. since 2014 starting at a base 100, with a logarithmic scale on the y-axis.*

|                        | Number of days | Final price (base 100) | Cumulative returns |
| ---------------------- | -------------- | ---------------------- | ------------------ |
| Before 2014            | 1,264.00       | 1,506,540.00           | 15,064.40          |
| Since 2014             | 3,916.00       | 8,260.30               | 81.60              |
| Ratio (before / since) | 0.32           | 182.38                 | 184.61             |

**Key takeaways:**
- This chart clearly highlights the massive difference in returns between an early adopter and everyone else.
- A hundred dollar investment made in July 2010 would have grown to over $1.5 million in less than two and a half years.
- If the same hundred had been invested at the start of 2014, it would have just grown to over $8,200 after more than 10 years, which is still an impressive return.
- However, this same investment, since 2014, doesn't seem likely to surpass the $1 million mark in the next couple of decades.

#### Distribution of Returns (Before vs. Since 2014)
![Bitcoin returns distributions 2014 chart](/images/2_BTC_returns_dist_2014.png)
*Histograms chart comparing the distributions of daily returns of bitcoin before vs. since 2014.*

|                        | Average return | Median return | Standard deviation | Min return | Max return | Skewness | Kurtosis |
| ---------------------- | -------------- | ------------- | ------------------ | ---------- | ---------- | -------- | -------- |
| Before 2014            | 0.0076         | 0.0031        | 0.0732             | -0.4914    | 0.5400     | -0.0867  | 10.5482  |
| Since 2014             | 0.0011         | 0.0011        | 0.0273             | -0.2242    | 0.2095     | -0.4911  | 6.2692   |
| Ratio (before / since) | 6.9091         | 2.8182        | 2.6813             | 2.1918     | 2.5776     | 0.1765   | 1.6825   |

**Key takeaways:**
- There is a noticeable difference in the price distributions across the different timeframes.
- Before 2014, bitcoin's average return was much higher compared to the post-2014 period, indicating greater profitability in earlier years. The median also dropped and became equal to the mean, suggesting that returns have become more symmetric, with fewer positive outliers.
- Since 2014, the standard deviation has dropped significantly, pointing to reduced price volatility in recent years.
- The range of returns has narrowed, with smaller extremes in both minimum and maximum values.
- Both periods show negative skewness, though it is more pronounced after 2014, suggesting a stronger tendency for more frequent returns below the mean in recent years.
- Kurtosis has decreased notably, meaning there are fewer extreme outliers since 2014, although the market still sees occasional sharp movements.

<br> <!-- Line break -->


### Price vs. Returns 🌀 <a name = "BTC_price_vs_returns"></a>
![Bitcoin price vs returns chart](/images/2_BTC_price_vs_returns.png)
*Scatter plot chart comparing the historical 90-day average price vs. 90-day average daily returns, with a logarithmic scale on the x-axis.*

**Key takeaways:**
- Before bitcoin's price reaches 1,000, the returns are more dispersed from zero but tend to skew positively.
- After crossing the 1,000 mark, returns become more stable, staying within the range of ±0.01.
- When comparing price (or market cap) with returns, there is a weak negative correlation of -0.16, much weaker than what was expected.

*For more details about this section, check the respective [Notebook](/notebooks/2_BTC_returns.ipynb).*

<br> <!-- Line break -->


### Bitcoin Volatility Over Time 🎢 <a name = "BTC_vlt"></a>
![Bitcoin volatility chart](/images/3.1_BTC_vlt.png)
*Line chart of the historical 90-day and 1-year volatility of the price of bitcoin.*

**Key takeaways:**
- The five biggest daily price changes occurred in 2010 and 2011, marking bitcoin’s early years as a period of intense volatility.
- From 2010 until early 2017, average volatility decreased by about 80%, reflecting the market’s maturation. However, it still experiences occasional spikes.
- After the 2017 spike, bitcoin resumed its downward trend in 2018.
- In recent years, bitcoin has become consistently more stable.
- The decrease in volatility over time is closely linked to the factors already mentioned like a larger market cap, increased liquidity, and also institutional involvement.
- This curve highlights bitcoin's evolution from a speculative asset to a more established component of the global financial system.

#### Comparison of Volatility With Other Assets
![Bitcoin volatility comparison chart](/images/3.1_BTC_vlt_comparison.png)
*Line chart comparing the historical 1-year volatility of the price of bitcoin with other major assets.*

**Key takeaways:**
- Before 2016, bitcoin's volatility was significantly higher than that of other major assets.
- In 2016, its volatility approached that of crude oil and US 10-year bonds, but they diverged again until 2020.
- When the pandemic hit, volatility spiked across all assets, with bitcoin's increase being relatively ordinary compared to others.
- Crude oil experienced an enormous volatility spike during this period, while US 10-year bonds also saw a substantial increase, both surpassing bitcoin's volatility for that year.
- In recent years, the cryptocurrency continues to lead in volatility, though it is now much closer to other volatile assets like crude oil.

<br> <!-- Line break -->


### Bitcoin Yearly Volatility Over Time 📊 <a name = "BTC_yearly_vlt"></a>
![Bitcoin yearly volatility chart](/images/3.1_BTC_yearly_vlt.png)
*Bar chart of the historical yearly volatility of the price of bitcoin.*

**Key takeaways:**
- The first four years were the most speculative, marking bitcoin's experimental phase.
- From 2014 onward, volatility began to stabilize, with noticeable spikes during rallies and crashes.
- Since 2017, there has been a clear downtrend in volatility, reflecting gradual maturity of this asset, as seen in the line chart before.
- The most volatile year was 2010, while 2023 was the least volatile.
- Volatility data for 2010 and 2024 are estimates, as these years are incomplete and were annualized.

<br> <!-- Line break -->


### Price vs. Volatility 📉 <a name = "BTC_price_vs_vlt"></a>
![Bitcoin price vs volatility chart](/images/3.1_BTC_price_vs_vlt.png)
*Scatter plot chart comparing the historical 90-day average price vs. 90-day price volatility, with a logarithmic scale on the x-axis.*

**Key takeaways:**
- Comparing price with volatility reveals a shift in the landscape, as anticipated.
- As the price (or market cap) rises, volatility tends to decrease.
- This trend becomes particularly noticeable after the price surpasses one thousand, and especially after it exceeds ten thousand, where volatility remains contained below 0.04.
- The correlation between price and volatility is moderately negative at -0.31.

<br> <!-- Line break -->


### Volatility vs. Returns 💸 <a name = "BTC_vlt_vs_return"></a>
![Bitcoin volatility vs returns chart](/images/3.1_BTC_vlt_vs_returns.png)
*Scatter plot chart comparing the historical 90-day price volatility vs. 90-day average daily returns.*

**Key takeaways:**
- Comparing returns with volatility creates an engaging chart that illustrates the maturation of the asset over the years.
- During the experimental phase, we observe distinct periods characterized by both high positive and negative returns.
- As the years progress, particularly after 2019, volatility significantly decreases, along with absolute returns, resulting in a concentrated cluster that tightens with more recent data.
- In periods of high volatility, we often see that returns are predominantly positive, as supported by a moderate correlation between volatility and returns of 0.4.

#### Comparison of Volatility vs. Returns With Other Assets
![Bitcoin volatility vs returns comparison chart](/images/3.1_BTC_vlt_vs_returns_comparison.png)
*Scatter plot chart comparing the average daily returns vs. daily price volatility across bitcoin and other major assets.*

**Key takeaways:**
- This chart illustrates the comparison of major assets concerning their volatility and returns since 2010.
- A notable cluster appears for all assets, except for crude oil and bitcoin.
- The cryptocurrency showcases significantly higher returns, but this comes with much greater volatility. In this case, it paid off the bet on risk.
- The impact of the 2020 situation positions crude oil poorly within this chart.

*For more details about this section, check the respective [Notebook](/notebooks/3.1_BTC_volatility.ipynb).*

<br> <!-- Line break -->


### Bitcoin Yearly Risk-Adjusted Returns Over Time ⚖️ <a name = "BTC_risk_adjusted"></a>
#### Sharpe Ratio
![Bitcoin yearly Sharpe chart](/images/3.2_BTC_yearly_sharpe.png)
*Bar chart of the historical yearly Sharpe ratio of bitcoin.*

**Key takeaways:**
- Adjusting returns for risk changes the yearly rankings while preserving their sign.
- The years marked by major rallies have the best Sharpe ratio.
- Although 2017 ranks third in returns, it has the highest Sharpe ratio, slightly surpassing the "golden year".
- During bitcoin’s experimental era, returns were so high that the Sharpe ratio remained significantly elevated despite extreme volatility.
- Typically, a Sharpe ratio above 1 is considered good, but most positive years for bitcoin have exceptionally high values.
- A negative Sharpe ratio means bitcoin underperformed the risk-free asset, which only happened in years when the cryptocurrency had negative returns.
- Generally, the more negative the Sharpe ratio, the worse the performance.
- However, extreme volatility can soften the impact of a negative ratio, as seen in 2018, where volatility was higher than in 2022 but the gap between returns and the average risk-free rate was larger.

#### Sortino Ratio
![Bitcoin yearly Sortino chart](/images/3.2_BTC_yearly_sortino.png)
*Bar chart of the historical yearly Sortino ratio of bitcoin.*

**Key takeaways:**
- When focusing on the Sortino ratio, which considers only downside volatility, there’s a noticeable shift in the absolute values across different years.
- This adjustment emphasizes the dominance of 2013, restoring it to first place, with 2017 now trailing in second.
- In 2012, downside volatility was at its lowest, and 2023 also experienced very low downside volatility, pushing these years to 3rd and 5th places, respectively.
- Ultimately, holding bitcoin for several years increases the likelihood of achieving a positive risk-adjusted return.

<br> <!-- Line break -->

### Value at Risk (VaR) and Expected Shortfall (CVaR) 🚨 <a name = "BTC_var"></a>
![Bitcoin var chart](/images/3.2_BTC_var.png)
*Histogram charts of the distribution of Monte Carlo simulated returns for bitcoin over 1-quarter (not "quater"), 1-year, and 5-year timeframes, with 1st and 5th percentile lines.*

| Time Horizon | VaR (95%) | CVaR (95%) | VaR (99%) | CVaR (99%) |
| ------------ | --------- | ---------- | --------- | ---------- |
| 90 days      | 0.264     | 0.362      | 0.425     | 0.500      |
| 365 days     | 0.298     | 0.498      | 0.623     | 0.773      |
| 1825 days    | -0.699    | -0.259     | 0.034     | 0.406      |

**Key takeaways:**
- Risk should be assessed not just by volatility but also by potential losses.
- While potential losses increase slightly from a quarter to a year, they decrease significantly over a five-year horizon.
- These calculations were done using the Monte Carlo method with data from 2019, when the asset was considered more mature.
- For example, after 90 days, there is a 95% chance that the investment will retain at least 73.6% of its original value.
- Investing in bitcoin is very risky over shorter periods like a quarter or a year.
- However, with a five-year horizon, the risk significantly reduces, with a 99% chance of retaining at least 96.6% of the investment, and an expected shortfall of 40.6%.

*For more details about this section, check the respective [Notebook](/notebooks/3.2_BTC_extra_risk_metrics.ipynb).*

<br> <!-- Line break -->


### Conclusions
- Bitcoin is an extraordinary asset that skyrocketed in value in a very short period, experiencing massive rallies and crashes.
- Its early returns were absolutely exceptional, vastly outperforming traditional assets.
- As the market expanded, became more liquid, and gained legitimacy, bitcoin's returns became much more moderate, though still higher than traditional assets.
- This outperformance came with intense volatility, especially during its experimental phase.
- Like its returns, bitcoin's volatility has decreased as the asset matured, yet it still surpasses traditional assets, maintaining its classic "high risk, high reward" dynamic.
- The risk-adjusted returns are impressive, with Sharpe ratios often exceeding 1 by a large margin during its positive years, well above the norm for traditional assets.
- Value at risk and expected shortfall show that the cryptocurrency is extremely risky over short-term horizons like a quarter or a year.
- However, over a five-year horizon, bitcoin’s risk decreases significantly, making long-term investment a very viable option, provided the blockchain remains secure and the market continues to take this asset seriously.


## Disclaimer
The content of this project is provided for **demonstration and educational purposes only**. The information presented here is **not intended** to be financial advice.


## License
GNU General Public License v3.0.
