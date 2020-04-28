# forex-algo


Data Science bootcamp project attempting to use previous technical indicators and a that has been expanded upon



<U>Data Sources used in project:</U>

<B>data/EURUSD_15m_BID.csv</B> - Price values for EURUSD pair in 15m increments

Variable Definitions:

Open: price of the pair at the start of the time interval
High: highest price of the pair within the duration of the time interval
Low: minimum price of the pair within the duration of the time interval
Close: price of the pair at the end of the time interval
Volume: amount of trades that occured within the duration of the time interval

<B>data/EURUSD_4h_profit.csv</B> - Results of the experiment done by @RodrigoSalas from Kaggle:https://www.kaggle.com/rsalaschile/forex-eurusd-dataset

 **Variable Definitions**
 
  - **RSI**: The relative strength index (RSI) is a momentum indicator that measures the magnitude of recent price changes to evaluate overbought or oversold conditions in the price of a stock or other asset.

$$RSI_\text{step one}= 100− \left[ \frac{100}{1+\frac{\text {Average gain}}{\text {Average loss}}} \right]$$

$$RSI_\text{step two}= 100− \left[ \frac{100}{1+\frac{\text{Previous average gain}*13+ \text{Current gain} }{\text{Average average loss}*13+ \text{Current loss} }} \right]$$
  
  - **Stoch**: A stochastic oscillator is a momentum indicator comparing a particular closing price of a security to a range of its prices over a certain period of time. The sensitivity of the oscillator to market movements is reducible by adjusting that time period or by taking a moving average of the result.

$$\%K = \left( \frac{C-L14}{H14-L14} \right) * 100 $$
 
  - **EMA**: An exponential moving average (EMA) is a type of moving average (MA) that places a greater weight and significance on the most recent data points. The below equations refer to the slope of the EMA over the last 20, 50, 100, and 200 days.
   
$$EMA_{Today} =  \left( \left( Value_{Today} * \frac{Smoothing}{1+Days} \right) \right) + EMA_{Yesterday}* \left( 1- \left( \frac{Smoothing}{1+Days} \right) \right)$$
   
  - ema20slope
  - ema50slope
  - ema100slope
  - ema200slope<br><br>
  - **std**: Standard Deviation, a statistical measure of a stock's volatility.

  
  - **mom**: This indicator compares the price of any given instrument to the price over a selected number of preceding periods. It is calculated by taking the difference in today's closing price and the closing price of n periods before. When the indicator is above 100 it means the price is rising, below 100 is represents a downward trend. 

$$MOM = \left( \frac{CP}{CPn} \right) * 100$$<br>

<center>    
   <b>where:</b> <br>
- C = most recent closing price<br>
- L14 = lowest price traded of the previous 14 trading sessions<br>
- H14 = highest price traded during the same 14-day period<br>
- %K = current value of the stochastic indicator<br>
</center>

- **BB_up_percen**:

- **cci**: Commodity Channel Index​ (CCI) is a momentum-based oscillator used to help determine when an investment vehicle is reaching a condition of being overbought or oversold. It is also used to assess price trend direction and strength.
  
$$CCI = \frac{\text{Typical Price} - MA}{.015*\text{Mean Deviation}}$$
  
$$\text{Typical Price} = \sum_{i=1}^{P} \frac {High + Low + Close}{3}$$

$$P = \text{Number of Periods}$$

$$MA = \text{Moving Average} = \frac {\sum_{i=1}^{P} \text{Typical Price}}{P}$$
 
$$\text{Mean Deviation} = \frac{\sum_{i=1}^{P} |\text{Typical Price} - \text{MA}|}{P}$$
  
  - **force**: The force index is a technical indicator that measures the amount of power used to move the price of an asset. The term and its formula were developed by psychologist and trader Alexander Elder and published in his 1993 book Trading for a Living. The force index uses price and volume to determine the amount of strength behind a price move.
  
$$\text{FI} \left( 1 \right) = \left( \text{CCP - PCP} \right) * \text{VFI} \left( 13 \right) = \text{13-Period EMA of FI} \left( 1 \right)$$<br>

<center>    
   <b>where:</b> <br>
- FI = Force Index <br>
- CCP = current close price <br>
- PCP = Prevjous close price <br>
- VFI = Volume force index <br>
- EMA = Exponential moving average 
</center>

- **macd**: The MACD (moving average convergence divergence) charts the difference between two exponential moving averages (a longer period EMA subtracted to a short period MA). The most common settings applied to MACD are 26 periods EMA and a 12 period EMA. The MACD is positive when the EMA(12) is above the EMA(26) indicating that the rate of change of the shorter period MA is higher than the longer period MA and this indicates positive momentum. On the other hand, it is negative when the EMA(12) is below the EMA(26), the rate of change of the shorter period MA is lower than the longer period MA indicating negative momentum.
  
$$MACD=EMA_{12} − EMA_{26}$$

- **bearsPower**: The Bears Power oscillator was developed by Alexander Elder. It measures the difference between the lowest price and a 13-day Exponential Moving Average (EMA), plotted as a histogram. If the Bears Power indicator is below zero, it means sellers were able to drive price below the EMA. If the Bears Power indicator is above zero, it means buyers were able to keep the lowest price above the EMA
  
$$\text{Bears Power} = Low - EMA_{13}$$

- **bullsPower**:
  
$$\text {Bulls Power} = High - EMA_{13}$$

- **WPR**: Williams %R, also known as the Williams Percent Range, is a type of momentum indicator that moves between 0 and -100 and measures overbought and oversold levels. The Williams %R may be used to find entry and exit points in the market. The indicator is very similar to the Stochastic oscillator and is used in the same way.
  
$$\text{Williams Percentage Range} = \frac{\text{Highest High} - \text{Close}}{\text{Highest High}-\text{Lowest Low}}$$

- **tipo**: type of operation (0=buy, 1=sell) **this is our target variable**
