# econ5200-lab12-instrumental-variables
# Instrumental Variables: Weak Instruments, Compliers and the Exclusion Restriction

## Objective

I examined how instrument strength, treatment-effect differences across individuals, and violations of the exclusion restriction affect instrumental variables (IV) estimates.

## Methodology

- Simulated data with a known treatment effect of 1.0 and an unobserved confounder that biased OLS estimates upward.
- Compared OLS and two-stage least squares (2SLS) estimates across different instrument strengths using first-stage F-statistics.
- Repeated the simulation 500 times to examine how weak instruments affect statistical significance and estimation accuracy.
- Replicated Card's (1995) analysis of returns to education using proximity to a four-year college as an instrument.
- Simulated direct effects of an instrument on the outcome to examine violations of the exclusion restriction.
- Wrote my own 2SLS function using two OLS regressions and checked the results against the `linearmodels` package.

## Key Findings

- **Weak instruments:** When the median first-stage F-statistic was 0.5, the median 2SLS estimate was 2.038, compared with the true effect of 1.0 and the median OLS estimate of 1.998. This showed how a very weak instrument can produce misleading estimates.
- **Statistical significance:** At a first-stage F-statistic of approximately 2.5, 31.4% of 2SLS estimates were statistically significant, but 75.2% of those estimates were more than 0.5 away from the true effect.
- **Card (1995) replication:** The first-stage F-statistic was 16.7. OLS estimated a return to schooling of 0.0740, while 2SLS estimated 0.1323. The difference highlighted the importance of understanding which population an IV estimate represents.
- **Exclusion restriction:** I found that a direct effect of the instrument larger than 0.25 would shift the simulated 2SLS estimate by more than 0.5, demonstrating how violations of the exclusion restriction can distort results.
- **Manual verification:** My 2SLS implementation reproduced the package estimate using two OLS regressions and independently calculated the first-stage F-statistic.
