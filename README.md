# CAPM-Regression-and-Volatility-Dynamics

This project examines how firm-level market betas and volatility components vary across industries and over time using historical U.S. equity return data. Using the Capital Asset Pricing Model (CAPM), I estimate rolling market betas for individual firms and decompose total stock volatility into systematic and idiosyncratic components. The analysis also investigates how beta and idiosyncratic volatility relate to future stock returns through portfolio sorting techniques.

This project was completed using Python and CRSP monthly stock return data spanning 1996–2023.

---

## Research Question

How do firm-level betas and volatilities (both systematic and idiosyncratic) vary across industries and over time, and how are they related to stock returns?

---

## Data

The dataset consists of:

* Monthly CRSP stock returns (1996–2023)
* Firm identifiers
* SIC industry classifications
* Value-weighted market returns used as a market proxy

To reduce computational intensity, ten firms were randomly selected from each industry during each year of the sample.

---

## Methodology

### 1. CAPM Beta Estimation

Firm-level market betas were estimated using rolling-window CAPM regressions:

[
r_{i,t} = \alpha_i + \beta_i MKT_t + \epsilon_{i,t}
]

where:

* (r_{i,t}) = excess return of stock (i)
* (MKT_t) = excess market return
* (\beta_i) = market beta
* (\epsilon_{i,t}) = idiosyncratic return component

Betas were estimated using rolling windows of:

* 12 months
* 24 months
* 36 months

---

### 2. Volatility Decomposition

Using CAPM residuals, total volatility was decomposed into:

* Systematic Volatility
* Idiosyncratic Volatility

The decomposition follows:

[
TVOL_{i,t} = SVOL_{i,t} + IVOL_{i,t}
]

where:

* Total Volatility = Standard deviation of stock returns
* Systematic Volatility = Market-driven risk component
* Idiosyncratic Volatility = Firm-specific risk component

---

### 3. Industry Analysis

For each industry-year combination, the following statistics were computed:

* Mean Beta
* Standard Deviation
* Skewness
* Kurtosis
* Percentiles

The analysis compares beta behavior across industries and across different estimation horizons.

---

### 4. Portfolio Sorting

Stocks were sorted into quintile portfolios based on:

* Market Beta
* Idiosyncratic Volatility

Average excess returns were then analyzed using both:

* Equal-weighted portfolios
* Value-weighted portfolios

---

## Key Findings

### Industry Differences in Beta

* The Services sector exhibited the highest average beta in the 12-month estimation window.
* The "Other" industry category displayed the highest average beta in both the 24-month and 36-month windows.
* Construction consistently showed the largest dispersion in beta estimates, indicating greater variability in systematic risk exposure.

### Volatility Dynamics

* Total, systematic, and idiosyncratic volatility followed similar time-series patterns.
* Idiosyncratic volatility consistently exceeded systematic volatility throughout the sample period.
* During periods of market stress, systematic volatility increased sharply, narrowing the gap between firm-specific and market-wide risk.

### Risk and Return

Portfolio sorting results provided insight into how beta and idiosyncratic volatility relate to realized stock returns across different weighting schemes and market environments.

---

## Python Packages Used

* Python
* Pandas
* NumPy
* Statsmodels
* SciPy
* Matplotlib

---

## Future Improvements

Potential extensions include:

* Multi-factor models (Fama-French 3-Factor and 5-Factor)
* GARCH volatility modeling
* Industry-specific factor analysis
* Out-of-sample forecasting of volatility
* Machine learning approaches to beta prediction
