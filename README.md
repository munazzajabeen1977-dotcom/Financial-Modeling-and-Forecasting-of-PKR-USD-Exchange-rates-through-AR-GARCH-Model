Financial Modeling and Forecasting through the AR–GARCH Model

The Autoregressive–Generalized Autoregressive Conditional Heteroskedasticity (AR–GARCH) model is one of the most widely used econometric approaches for modeling and forecasting financial time series. It combines an Autoregressive (AR) model for capturing the dynamics of the conditional mean with a Generalized Autoregressive Conditional Heteroskedasticity (GARCH) model for estimating time-varying volatility. This combination is particularly useful in financial markets, where asset returns often exhibit characteristics such as autocorrelation, volatility clustering, leptokurtosis (fat tails), and heteroskedasticity.
________________________________________
Concept of the AR Model

The Autoregressive (AR) model assumes that the current value of a financial time series depends on its own previous values. An AR model of order p, denoted as AR(p), can be expressed as:

Y_t=c+∑_(i=1)^p▒ϕ_i  Y_(t-i)+ε_t

where:

	Y_t= value of the financial series at time t 
  
	c= constant term 
  
	ϕ_i= autoregressive coefficients 
  
	Y_(t-i)= lagged observations 
  
	ε_t= random error term 
  
The AR component captures the predictable behavior or persistence in financial returns. However, it assumes that the variance of the error term remains constant over time, which is rarely true for financial data.
________________________________________
Concept of the GARCH Model

To overcome the limitation of constant variance, the GARCH model was developed by Bollerslev (1986) as an extension of Engle's (1982) ARCH model. GARCH models the conditional variance as a function of both previous forecast errors and previous conditional variances.

The standard GARCH(1,1) model is represented as:

Mean Equation

Y_t=μ+ε_t

Error Term

ε_t=σ_t z_t

where
	
  z_t∼N(0,1)

Variance Equation

σ_t^2=ω+αε_(t-1)^2+βσ_(t-1)^2

where:
	
  σ_t^2= conditional variance 
	
  ω= constant 
	
  α= ARCH effect (impact of recent shocks) 
	
  β= GARCH effect (volatility persistence) 

The model requires:

ω>0,α≥0,β≥0,α+β<1

A high value of (αⓜ+β)indicates persistent volatility, a common characteristic of stock market returns.
________________________________________
AR–GARCH Model

The AR–GARCH model integrates both the AR and GARCH processes into a single framework.

Mean Equation

Y_t=c+∑_(i=1)^p▒ϕ_i  Y_(t-i)+ε_t

Error Equation

ε_t=σ_t z_t

Variance Equation

σ_t^2=ω+∑_(i=1)^q▒α_i  ε_(t-i)^2+∑_(j=1)^p▒β_j  σ_(t-j)^2

The AR component explains expected returns, while the GARCH component models changing market volatility.
________________________________________
Steps in Financial Modeling Using the AR–GARCH Model

Step 1: Data Collection

	Monthly Exchange rates data are collected from the State Bank of Pakistan  (January 2000 to June 2026)
________________________________________
Step 2: Data Pre-processing

The collected exchange rate series are transformed into continuously compounded returns:

R_t=ln⁡(〖EX〗_t/〖EX〗_(t-1) )

where:

  R_t= log return 
	
  〖EX〗_t= current exchange rates
	
  〖EX〗_(t-1)= previous exchange rates

Log returns are generally stationary and suitable for volatility modeling.
________________________________________
Step 3: Stationarity Testing

Exchange rate return series are tested for stationarity using:
	
  Augmented Dickey–Fuller (ADF) test 

Stationarity ensures reliable parameter estimation.
________________________________________
Step 4: Selecting the AR Order

Autocorrelation Function (ACF) and Partial Autocorrelation Function (PACF) plots help identify the appropriate lag order.

Information criteria such as:
	
  Akaike Information Criterion (AIC) 
	
  Bayesian Information Criterion (BIC) 
	
  Hannan–Quinn Criterion (HQIC) 

are used to select the optimal AR(p) model.
________________________________________
Step 5: Estimating the AR Model

The AR model is estimated first to capture the conditional mean dynamics. The residuals obtained from the AR model are then analyzed for heteroskedasticity.
________________________________________
Step 6: Testing for ARCH Effects

Before fitting a GARCH model, the residuals from the AR model are examined using:
	
  Engle's ARCH-LM Test 

If significant ARCH effects are present, a GARCH model is appropriate.
________________________________________
Step 7: Estimating the GARCH Model

The conditional variance equation is estimated simultaneously with the AR mean equation.

The most common specification is:
	
  AR(1)-GARCH(1,1) 

Maximum Likelihood Estimation (MLE) is generally employed to estimate the model parameters.
________________________________________
Step 8: Model Diagnostics

Several diagnostic tests are performed to evaluate model adequacy:

  Ljung–Box test for residual autocorrelation 

  Ljung–Box test on squared residuals 

  ARCH-LM test 
	
  Jarque–Bera normality test 

  Information criteria (AIC and BIC) 

A well-specified model should have residuals that resemble white noise and no remaining ARCH effects.
________________________________________
Step 9: Forecasting

The fitted AR–GARCH model generates forecasts for:
	
  Future returns (mean forecasts) 
	
  Future volatility (variance forecasts) 

Volatility forecasts are especially valuable for financial decision-making because they provide insights into the expected level of market risk.
________________________________________
Advantages of the AR–GARCH Model

•	Simultaneously models returns and volatility. 

•	Captures volatility clustering commonly observed in financial markets. 

•	Produces more accurate volatility forecasts than constant-variance models.

•	Improves financial risk measurement and portfolio management. 

•	Widely accepted in academia and industry. 

•	Flexible enough to incorporate different error distributions (e.g., Student's t distribution) for heavy-tailed financial returns.

•	Suitable for high-frequency and daily financial data. 
________________________________________
Limitations of the AR–GARCH Model

•	Assumes a linear relationship in the mean equation. 

•	Standard GARCH does not capture asymmetric responses of volatility to positive and negative shocks; models such as EGARCH or GJR-GARCH may be more appropriate in such cases. 

•	Sensitive to structural breaks and regime changes. 

•	Requires careful model specification and parameter selection. 

•	Performance may decline when financial markets experience sudden, unprecedented events. 
