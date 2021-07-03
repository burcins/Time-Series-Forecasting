# Time-Series-Forecasting

The goal of this work is to forecast daily cash demands of ATMs (Automated Teller Machines) for the following month, by using 1 year long logs of loaded and withdrawed cashes on daily basis.

The dataset includes 3 features: CashIn, CashOut, and Date;

    CashIn : contains the total deposit amount of the ATM for the given date.
    CashOut : the withdrawal values of given date on ATM.
    Date : Daily given dates

It contains 1.186 observations at total which corresponds to 1.186 days starting from 01.01.2016 to 03.31.2019. Eventually it has been expected to forecast the CashIn and CashOut values between 2019-04-01 and 2019-04-30 separately.

Initially, I plan to do Exploratory Data Analysis to understand raw data and add additional features generated from dates to streghten the capability of implemented algorithms.

I would like to mention that, since I have no evidence to know the location of the ATM, I tried not to add location specific informations as features. But if I knew the exact location, adding a flag to local holidays would be a good indicator, or even location specific weather might be useful to predict ATM usage. But for now, I only stick to the date column to derive new features. However, I assume that the first and last business days of a month have similar effects on cash flow in many locations so I added them as dummy features.

Subsequent to these data preperation and understanding steps, structure of this project is following a path to implement several approaches under separate subtopics to forecast cash demands. These topics can be summarized as below;

    Time series methods that predict future cash need based on the past values
    Using LSTM to predict future cash demands based on the past values
    Supervised learning methods that predict future cash demand by using derived features and treat the dataset as static data

Last but not least, since there are both loaded cash and withdrawed cash are tracked in same time lag, this dataset can be treated as multivariate time series with dependencies to each other. However, in this study, I have no clue that, this cash flow amounts have some impact on each other. Of course correlation value between them may explain some part of it, but as it is suggested on the study guidance section, I will treat these CashIn and CashOut values separately as independent univariate time series, so I will set the models one by one for each of them separately.

Eventually, final prediction method will be decided and implemented and then exported as csv file for both loaded cash and withdrawed cash amounts.

It should be noted that, this study has been handled in a restricted time period, so analyses in subsections kept limited. There is unlimited scope, both vertically and horizontally, to improve results.
