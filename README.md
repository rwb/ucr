#### Exploring Changes in City-Level Murder Rates During the Ferguson Era: A Partial Identification Analysis

* historical events: police killings of Michael Brown in August 2014 (Ferguson, MO) and Freddie Gray in April 2015 (Baltimore, MD)
* FBI Director James Comey and the "Ferguson effect": "Far more people are being killed in America’s cities this year than in many years."
* emphasis of this study: changes in murder rates, comparing 2013 to 2015
  
---
#### Prior Literature

* Pyrooz et al. (2016): examined changes in crime rates in large U.S. cities (105 cities with >200k population in 2010; compared 12 months before and after the Brown killing in Ferguson); no evidence of significant change.
* Rosenfeld (2015): distinguishes between 2 different Ferguson effects; studied 56 large American cities; 40 cities increased and 16 cities decreased from 2014-2015; considerable heterogeneity in city-specific trends.
* Rosenfeld and Wallman (2019); national study of the "spike" in murder rates from 2014-15; 53 large American cities studied from 2010-2015; effort to study the effect of arrest rates on murder rates.
* Gaston et al. (2019) studied homicide rates using CDC data from 2014-2016; goal was to determine whether police killings and civil unrest related to police killings and the opioid epidemic drove homicide rates higher in 586 urban American counties (population > 100k); found evidence in support of the Ferguson effect (particularly in the case of Black victim homicides).
* important themes in the literature: missing data, strong identification assumptions, and ambiguity about the proper independent variable(s) to consider.

---
#### Two Analyses

* let *p* be the probability that a city drawn at random experiences an increase in its murder rate from 2013 to 2015.
* study #1: a sign test of the hypothesis that *p* = 1/2 (i.e., the murder rate is equally likely to increase or decrease from 2013 to 2015 for a randomly drawn city).
* let $\Delta$ be a city's murder rate in 2015 minus its murder rate in 2013.
* study #2: what is the typical change in the murder rate from 2013 to 2015?
* is *p* > 1/2?
* is the typical $\Delta$ > 0?

---
#### Dataset/Methods

* sample: N = 82 American cities with at least 250,000 population in either 2013, 2014, or 2015.
* number of murders is based on the FBI's Uniform Crime Reporting Program for the years 2013 and 2015.
* population size is reported for each city's jurisdiction for the years 2013-2015.
* the murder rate is expressed as the number of murders divided by the population size (on a per 100,000 population scale)

| City | 2013 Murders | 2013 Population | 2015 Murders | 2015 Population | 2013 Rate | 2015 Rate | +/- |
|:-----|-------------:|----------------:|-------------:|----------------:|----------:|----------:|----:|
| Albuquerque | 37    | 558,165         | 43           | 559,721         | 6.629     | 7.682     | +   |
| Anaheim     | 11    | 345,320         | 18           | 349,471         | 3.185     | 5.151     | +   |
| Anchorage   | 14    | 299,455         | 26           | 301,239         | 4.675     | 8.631     | +   |
| Arlington   | 18    | 378,765         | 8            | 387,565         | 4.752     | 2.064     | -   |

*
*
*

| City | 2013 Murders | 2013 Population | 2015 Murders | 2015 Population | 2013 Rate | 2015 Rate | +/- |
|:-----|-------------:|----------------:|-------------:|----------------:|----------:|----------:|----:|
| Tulsa          | 60    | 394,498         | 55           | 401,520         | 15.209    | 13.698    | -   | 
| Virginia Beach | 17    | 450,687         | 19           | 452,797         | 3.772     | 4.196     | +   |
| Washington DC  | 103    | 646,449         | 162         | 672,228         | 15.933     | 24.099   | +   |
| Wichita        | 15    | 386,486         | 27           | 389,824         | 3.881     | 6.926     | +   |

* A problem is that for 4 of the 82 cities, it is not possible to tell whether the murder rate increased or decreased or how much it changed.

| City | 2013 Murders | 2013 Population | 2015 Murders | 2015 Population | 2013 Rate | 2015 Rate | +/- |
|:-----|-------------:|----------------:|-------------:|----------------:|----------:|----------:|----:|
| Honolulu       | NA    | NA         | 15           | 999,307         | NA    | 1.501    | ?   | 
| Newark | 112    | 278,246         | NA           | NA         | 40.252     | NA     | ?   |
| Portland  | 14    | 609,136         | NA         | NA         | 2.298     | NA   | ?   |
| Raleigh        | 12    | 428,993         | NA           | NA         | 2.797     | NA     | ?   |

* analysis objective: develop a valid estimate of *p*.
* 48 cities experienced an increase
* 30 cities experienced a decrease
* 4 cities had missing information
* based on law of total probability, estimate *p* = p(observed)*p(increase|observed)+p(missing)*p(increase|missing)
* in addition to *p*, we will calculate a 95% confidence interval for *p*.
* will use the Jeffreys procedure to calculate the confidence interval (i.e., invert the beta distribution with shape parameters 1/2+number of increases and 1/2+number of decreases).

---
#### Missing-At-Random Results

* recall that *p* = p(observed)*p(increase|observed)+p(missing)*p(increase|missing)
* p(observed) = 78/82
* p(increase|observed) = 48/78
* p(missing) = 4/82
* p(increase|missing) = ?/4
* missing-at-random (mar) estimate = p(observed)*p(increase|observed)+p(missing)*p(increase|observed)
* mar.est = 78/82 x 48/78 + 4/82 x 48/78 = 0.615
* 95% confidence interval around mar.est = [0.505,0.718]
* reject Ho that p = 0.5

---
#### Bounds Analysis

* minimum value of *p* consistent with the data: 78/82 x 48/78 + 4/82 x 0/4 = 0.585
* maximum value of *p* consistent with the data: 78/82 x 48/78 + 4/82 x 4/4 = 0.634
* notice that 0.634-0.585 = 0.049 which is the same as 4/82 (fraction of cases that are missing)
* 95% confidence interval for the lower and upper bounds: LB: [0.462,0.701] and UB: [0.511,0.745]

---
#### Conclusions

* murder is among the best measured crimes in the United States.
* still, our principal law enforcement-based measure of murder (the UCR) is based on voluntary participation by agencies.
* each year, some agencies across the United States are not represented in the nation's crime statistics.
* when we compare crime statistics in different years, the problem is compounded.
* one solution to this problem is to assume that the patterns among the observed agencies are replicated among the missing agencies.
* we call this the missing-at-random (MAR) assumption.
* advantage of MAR: we can get a point estimate with a confidence interval.
* disadvantage of MAR: we can't test the assumption.
* consequence of relying on it: we understate the uncertainty of our analysis.
* standard MAR analysis would lead us to reject the hypothesis that *p* = 0.5 (a city drawn at random is equally likely to have experienced an increase or a decrease in its murder rate from 2013 to 2015).
* a partial identification analysis leads us to the conclusion that our sample *p* must be somewhere between 0.585 and 0.634.
* The confidence interval around the lower bound estimate of 0.585 is [0.462,0.701]; since this confidence interval includes 0.5, we now fail to reject the hypothesis that *p* = 0.5.
* The data are simply not strong enough to tell us whether *p* is actually greater than 0.5.
