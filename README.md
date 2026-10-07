# Diagnosing a Flawed Risk Model — VaR, Expected Shortfall & Monte Carlo

## Objective
I checked how assuming normally distributed returns affects portfolio risk estimates and compared methods for measuring tail losses.

## Methodology
- I examined 2,520 simulated daily returns for a $10 million portfolio.
- I compared VaR and Expected Shortfall using normal, fitted Student-t, and historical methods.
- I compared ordinary Monte Carlo with antithetic pairs using 50,000 paths.
- I ran the supplied risk_metrics.py module and its self-tests.
- I revised the AI backtest prompt to specify the units and breach rule, then checked the results against my own counts.

## Key Findings
- My normal 99% VaR was $276,519, compared with historical VaR of $316,912. The normal estimate was $40,393 (12.7%) too low.
- At 95%, normal VaR was 3.5% higher than historical VaR. This showed me that the direction of the error depends on the confidence level.
- My fitted Student-t had 4.58 degrees of freedom. Its 99% Expected Shortfall was $426,060, compared with $391,464 for the historical method and $317,193 for the normal method.
- Antithetic pairs reduced my standard error by a factor of 1.26 and reduced variance by 37.0%.
- Normal 99% VaR was breached on 43 of 2,520 days (1.71%), compared with 26 days (1.03%) for historical VaR. Both matched my hand counts.
- I used the same returns to estimate and check VaR, so this was an in-sample check.

## Files
- lab_ch05_diagnostic.ipynb: my calculations, answers, chart, and backtest.
- risk_metrics.py: the supplied risk functions and self-tests.
