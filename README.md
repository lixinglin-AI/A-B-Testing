# A/B Testing Analysis

This project demonstrates an A/B testing analysis using Bayesian methods. The goal is to analyze the performance of two groups (control and treatment) and determine if there's a significant difference in their conversion rates.

---

## Dataset Overview

The dataset is loaded from an online source. It includes:

- **Group**: Specifies whether the user is in the `control` or `treatment` group.
- **Converted**: Indicates if the user performed the desired action.

---

## Step 1: Explore Conversion Rates

The first step is to calculate the conversion rates for both groups:

- **Control Group**: Conversion rate derived from users in the `control` group.
- **Treatment Group**: Conversion rate derived from users in the `treatment` group.

This provides a baseline comparison.

---

## Step 2: Bayesian Priors

### Assumption of Beta Distribution

- A Beta distribution is used as a prior for the conversion rates.
- Parameters:
  - **Alpha (α)**: Controls the shape of the distribution.
  - **Beta (β)**: Influences the mass toward lower or higher values.

### Insights:

- Increasing **β** (relative to **α**) shifts the mass toward smaller conversion rates.
- Increasing both **α** and **β** reduces uncertainty by making the distribution more concentrated.

---

## Step 3: Updating with Observed Data

After loading the dataset, the priors are updated with observed data to calculate the posterior distributions for each group:

- **Posterior Distribution**: Updated belief about the conversion rates after observing data.
- Parameters are adjusted based on:
  - Successes (number of conversions).
  - Failures (number of non-conversions).

---

## Step 4: Decision Making with Credible Intervals

The 95% credible intervals are calculated to compare the control and treatment groups. This helps identify if the differences are statistically significant.

### Results:

- **Control Group 95% Credible Interval**: `[0.1187, 0.1221]`
- **Treatment Group 95% Credible Interval**: `[0.1173, 0.1206]`

### Interpretation:

The overlap between these intervals suggests no significant difference in conversion rates between the groups.

---

## Step 5: Experimenting with Priors

Different priors reflecting specific assumptions (e.g., a 10% conversion rate) were applied to analyze their influence on posterior distributions.

### Observations:

- Priors closer to a 10% conversion rate shifted the posterior distributions accordingly.
- Adjusting priors allows for incorporating domain knowledge into the analysis.

---

## Conclusion

This A/B testing analysis demonstrates:

1. **Exploring conversion rates**: Provides a baseline understanding of the groups.
2. **Using Bayesian methods**: Enables flexible updates to beliefs with observed data.
3. **Decision-making with credible intervals**: Offers clear insights into group differences.

Bayesian analysis provides a robust framework for understanding A/B testing results while incorporating prior knowledge.

---

## References

- Dataset Source: [Kaggle](https://www.kaggle.com/datasets)
- Documentation: [Bayesian Methods](https://en.wikipedia.org/wiki/Bayesian_statistics)
