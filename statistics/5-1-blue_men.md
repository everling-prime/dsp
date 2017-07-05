[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> How many people are between 5'10" and 6'1"?

```
import scipy.stats

mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)

five10 = 177.8
six1 = 185.45
dist.cdf(six1) - dist.cdf(five10)
```
0.34372201280887077, or about 34%
