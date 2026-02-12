# A/B Testing Case Study: Social-Proof Badge in Food Delivery

## Project Overview
This project evaluates whether adding a **social-proof badge** (e.g., "Popular choice") to restaurant listings improves user ordering behavior in a food-delivery application.

A randomized A/B experiment was simulated to measure the impact on conversion while ensuring order quality was not negatively affected.



## Objective
Determine whether displaying a social-proof badge increases order conversions 

## Experiment Design
- Experiment type: A/B test
- Randomization: User-level
- Traffic split: 50/50
- Duration: 9 days
- Sample size: ~56,000 users
- Unit of analysis: user

**Variants**
- Control → No badge
- Treatment → Social-proof badge displayed
- 
## Data Dictionary

This project uses a synthetic dataset simulating user behavior in a food-delivery application during an A/B experiment.

Each row represents a user exposed to either the control or treatment variant.

### Table 

| Field Name       | Type    | Description                                                   | Example      |
|------------------|---------|---------------------------------------------------------------|-------------|
| user_id          | STRING  | Unique identifier for each user                               | U_000123    |
| date             | DATE    | Experiment exposure date                                      | 2025-12-01  |
| variant          | STRING  | Experiment group assignment (control or treatment)            | treatment   |
| ordered          | INTEGER | Whether the user placed an order (1 = yes, 0 = no)            | 1           |
| menu_clicks      | INTEGER | Number of menu interactions                                   | 4           |
| time_to_order    | FLOAT   | Time taken to place an order (only available for orders)      | 11.5        |
| order_cancelled  | INTEGER | Whether the order was cancelled (1 = yes, 0 = no)             | 0           |
| order_value      | FLOAT   | Value of the order (0 if no order placed)                     | 6.20        |




## Metrics

**Primary Metric**
- Order conversion rate

**Secondary Metric**
- Time to order

**Guardrail Metric**
- Cancellation rate


## Hypothesis

**Null Hypothesis (H₀)**  
Displaying a social-proof badge does not change order conversion rate.

**Alternative Hypothesis (H₁)**  
Displaying a social-proof badge increases order conversion rate.


## Methodology
The experiment was analyzed using:
- Chi-square test to validate randomization balance
- Two-proportion z-test for conversion rate comparison
- Two-proportion z-test for cancellation rate comparison

Effect size was calculated to evaluate business impact.



## Results
- Conversion increased from ~20% (control) to ~21% (treatment), a ~1 percentage point lift (~5% relative improvement)
- Time-to-order decreased in the treatment group
- Cancellation rate showed no statistically significant change



## Conclusion
The social-proof badge improved order conversion without causing measurable harm to order quality.

Based on these results, we recommend rolling out the feature while continuing to monitor cancellation rates post-launch.
