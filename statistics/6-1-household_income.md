[Think Stats Chapter 6 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2007.html#toc60) (household income)

```
import numpy as np

def InterpolateSample(df, log_upper=6.0):
    """Makes a sample of log10 household income.

    Assumes that log10 income is uniform in each range.

    df: DataFrame with columns income and freq
    log_upper: log10 of the assumed upper bound for the highest range

    returns: NumPy array of log10 household income
    """
    # compute the log10 of the upper bound for each range
    df['log_upper'] = np.log10(df.income)

    # get the lower bounds by shifting the upper bound and filling in
    # the first element
    df['log_lower'] = df.log_upper.shift(1)
    df.loc[0, 'log_lower'] = 3.0

    # plug in a value for the unknown upper bound of the highest range
    df.loc[41, 'log_upper'] = log_upper
    
    # use the freq column to generate the right number of values in
    # each range
    arrays = []
    for _, row in df.iterrows():
        vals = np.linspace(row.log_lower, row.log_upper, row.freq)
        arrays.append(vals)

    # collect the arrays into a single sample
    log_sample = np.concatenate(arrays)
    return log_sample


import hinc
income_df = hinc.ReadData()

log_sample = InterpolateSample(income_df, log_upper=6.0)

log_cdf = thinkstats2.Cdf(log_sample)

sample = np.power(10, log_sample)

cdf = thinkstats2.Cdf(sample)
```
>Compute the median, mean, skewness and Pearson’s skewness of the resulting sample. What fraction of households report a taxable income >below the mean? How do the results depend on the assumed upper bound?
```
print(Mean(sample))
print(Median(sample))
print(Skewness(sample))
print(PearsonMedianSkewness(sample))
```
74278.7075312  
51226.4544789  
4.94992024443  
0.736125801914  


> What fraction of households report a taxable income below the mean?  

`print(cdf.Prob(Mean(sample)))`

0.660005879567


```
