# CoinMinD_R_Package


# CoinMinD  
[![CRAN version](https://www.r-pkg.org/badges/version/CoinMinD)](https://cran.r-project.org/package=CoinMinD)

[![CRAN Downloads](https://cranlogs.r-pkg.org/badges/CoinMinD)](https://cran.r-project.org/package=CoinMinD)

[![License: GPL (≥ 2)](https://img.shields.io/badge/license-GPL%20(%E2%89%A52)-blue.svg)](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html)

## Overview  

**CoinMinD** (Simultaneous Confidence Intervals for Multinomial Proportions) is an R package that provides an extensive set of **classical** and **Bayesian** procedures for computing **simultaneous confidence intervals (SCIs)** for multinomial proportions.  
It integrates a range of established statistical methods in one interface, helping users compare, visualize, and interpret interval estimates for categorical outcomes.

---

## Key Features  

- Implements **eight major SCI methods** for multinomial proportions.  
- Supports both **frequentist** and **Bayesian Dirichlet** frameworks.  
- Handles **equal and unequal prior settings** for Bayesian inference.  
- Includes built-in visualization and summary functions.  
- Written purely in **R**, ensuring platform independence and easy installation.

---

## Implemented Methods  

### 🔹 Classical (Frequentist) Methods  

| Method | Reference | Description |
|--------|------------|-------------|
| **Wilson (WS)** | Wilson (1927) | Adaptation of the Wilson score interval for multinomial proportions; provides improved coverage accuracy. |
| **Quesenberry & Hurst (QH)** | Quesenberry & Hurst (1964) | Extends chi-square-based binomial intervals to the multinomial case with simultaneous coverage control. |
| **Goodman (GM)** | Goodman (1965) | Constructs family-wise simultaneous confidence intervals using a chi-square adjustment. |
| **Wald (WALD)** | Wald (1939) | Classical normal approximation intervals; straightforward but may miscover for small samples. |
| **Wald with Continuity Correction (WALDCC)** | — | Modified Wald intervals that include a continuity correction to improve coverage. |
| **Fitzpatrick & Scott (FS)** | Fitzpatrick & Scott (1987) | Uses moment-matching and chi-square approximations; often narrower than Goodman’s intervals. |
| **Sison & Glaz (SG)** | Sison & Glaz (1995) | Based on saddlepoint and moment approximations, offering accurate coverage for small to moderate sample sizes. |
| **Friedrich et al. (2017)** | Friedrich, Konietschke & Pauly (2017) | Provides simultaneous confidence intervals derived from multiple contrast tests; flexible and modern approach for multinomial data. |

---

### 🔹 Bayesian Methods  

| Method | Description |
|--------|-------------|
| **BMDE (Bayesian Dirichlet – Equal Prior)** | Constructs simultaneous credible intervals under a Dirichlet posterior assuming equal prior parameters. |
| **BMDU (Bayesian Dirichlet – Unequal Prior)** | Allows user-specified (unequal) priors to reflect prior knowledge or asymmetry among categories. |

Both Bayesian methods yield either **equal-tail** or **highest posterior density (HPD)** intervals based on posterior draws from the Dirichlet distribution.

---

## Installation  

Install the latest CRAN release:

```r
install.packages("CoinMinD")
````

---

## Example Usage

```r
# Load the CoinMinD package
library(CoinMinD)

# Example data: counts for four categories
x <- c(12, 18, 25, 15)

# Compute simultaneous confidence intervals using different methods

# Classical methods
res_goodman <- GM(x, alpha = 0.05)
res_wald <- WALD(x, alpha = 0.05)
res_waldcc <- WALDCC(x, alpha = 0.05)
res_wilson <- WS(x, alpha = 0.05)
res_qh <- QH(x, alpha = 0.05)
res_fs <- FS(x, alpha = 0.05)
res_sg <- SG(x, alpha = 0.05)

# Bayesian methods
res_bmde <- BMDE(x, p = 0.1)
res_bmdu <- BMDU(x, d = 2)

# Print summaries
print(res_goodman)
print(res_wald)
print(res_waldcc)
print(res_wilson)
print(res_qh)
print(res_fs)
print(res_sg)
print(res_bmde)
print(res_bmdu)

```

---

## Documentation

* 📘 **CRAN Page:** [https://cran.r-project.org/package=CoinMinD](https://cran.r-project.org/package=CoinMinD)
* 📄 **Reference Manual:** [PDF Manual](https://cran.r-project.org/web/packages/CoinMinD/CoinMinD.pdf)
* 🧾 **Vignettes:** Check `vignette("CoinMinD")` for detailed examples and comparisons of methods.

---

## Citation

If you use this package in academic work, please cite:

```
Subbiah, M. (2025). CoinMinD: Simultaneous Confidence Intervals for Multinomial Proportions.
R package version 1.2.2. https://CRAN.R-project.org/package=CoinMinD
```

---

## Contributing

Contributions and feedback are welcome!
To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature-newmethod`)
3. Commit your changes
4. Submit a Pull Request

---

## License

**CoinMinD** is licensed under the **GPL (≥ 2)** license.
See the [LICENSE](LICENSE) file for full details.

---

## Acknowledgments

The package consolidates a wide range of interval estimation techniques developed by Wilson (1927), Quesenberry & Hurst (1964), Goodman (1965), Fitzpatrick & Scott (1987), Sison & Glaz (1995), and Friedrich et al. (2017), among others.
Grateful acknowledgment is given to the R community and contributors for their feedback and continued support.

---

*Last updated: October 2025*

