# ENS Stock Return Prediction Challenge

### Files
Before explaining the project, here are the description of each file. 
| Files | Description |
| ------ | ------ |
| `StockPrediction.ipynb` | All data analysis / processing and machine learning algorithms |
| `x_train2.csv` | Input file |
| `y_train2.csv` | Output file |

### Challenge context
Quantitative investment strategies require the analysis of historical data to predict the trend of a stock in a near future. However, the extremely low level of signal / noise makes it a very challenging problem. Digging slight information among the enormous amount of available data in the market is a key goal for Qube RT. To do so, Machine Learning techniques can be used to make better trading decisions through deep analysis of thousands of different data sources. In a financial world in constant movement, it is extremely difficult to detect patterns that make a stock move up or down. This challenge is an illustration of the financial stock prediction.

### Challenge goals
The proposed challenge aims at predicting the return of a stock in the US market using historical data over a recent period of 20 days. The one-day return of a stock j on day t with price P_j^t (adjusted from dividends and stock splits) is given by:

<p align="center">
  <img src="https://github.com/lbenbaccar/ENS-Challenge-Stock-Return-Prediction/blob/main/formula1.PNG" alt="formula1" width="200"/>
</p>

In this challenge, we consider the residual stock return, which corresponds to the return of a stock without the market impact. Historical data are composed of residual stock returns and relative volumes, sampled each day during the 20 last business days (approximately one month). The relative volume \mathcal{V}_j^t at time t of a stock j among the n stocks is defined by:

<p align="center">
  <img src="https://github.com/lbenbaccar/ENS-Challenge-Stock-Return-Prediction/blob/main/formula2.PNG" alt="formula2" width="250"/>
</p>

where V_j^t is the volume at time t of a stock j. We also give additional information about each stock such as its industry and sector.

The metric considered is the accuracy of the predicted residual stock return sign.

### Data description
We did this challenge with 2 datasets provided as csv file, split between inputs and outputs.

Input datasets comprise 47 columns: the first ID column contains unique row identifiers while the other 46 descriptive features correspond to:
| Input | Description |
| ------ | ------ |
| `DATE` | an index of the date (the dates are randomized and anonymized so there is no continuity or link between any dates) |
| `STOCK` | an index of the stock |
| `INDUSTRY` | an index of the stock industry domain (e.g., aeronautic, IT, oil company) |
| `INDUSTRY_GROUP` | an index of the group industry |
| `SUB_INDUSTRY` | a lower level index of the industry |
| `SECTOR` | an index of the work sector |
| `RET_1 to RET_20` | the historical residual returns among the last 20 days (i.e., RET_1 is the return of the previous day and so on) |
| `VOLUME_1 to VOLUME_20` | the historical relative volume traded among the last 20 days (i.e., VOLUME_1 is the relative volume of the previous day and so on) |

Output datasets are only composed of 2 columns:
| Output | Description |
| ------ | ------ |
| `ID` | the unique row identifier (corresponding to the input identifiers) |
| `RET` | the sign of the residual stock return at time t (binary) |

100 000 observations (i.e. lines) are available for both datasets.

### More explanation
[Link of the ENS challenge](https://challengedata.ens.fr/challenges/23)

[Link of Qube Research & Technologies challenge platform](https://challengedata.qube-rt.com/)
