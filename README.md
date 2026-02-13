# 📌 A/B Testing Case Study: Social-Proof Badge in Food Delivery
## Project Overview

This project evaluates whether adding a **social-proof badge** (e.g., "Popular choice") to restaurant listings improves user ordering behavior in a food-delivery application.

A randomized A/B experiment was simulated to measure the impact on **conversion rate** while ensuring **order quality metrics** were not negatively affected.



## 🎯 Objective

Determine whether displaying a social-proof badge increases **order conversion rate**.


## 🧪 Experiment Design

* Experiment type: A/B test
* Randomization: User-level
* Traffic split: 50/50
* Duration: 9 days
* Sample size: ~56,000 users
* Unit of analysis: user

**Variants**

* Control → No badge
* Treatment → Social-proof badge displayed


## 📘 Data Dictionary

This project uses a **synthetic dataset** simulating user behavior during a food-delivery A/B experiment.

Each row represents a user exposed to either the control or treatment variant.

| Field Name      | Type    | Description                      | Example    |
| --------------- | ------- | -------------------------------- | ---------- |
| user_id         | STRING  | Unique identifier for each user  | U_000123   |
| date            | DATE    | Experiment exposure date         | 2025-12-01 |
| variant         | STRING  | Control or treatment group       | treatment  |
| ordered         | INTEGER | Whether the user placed an order | 1          |
| menu_clicks     | INTEGER | Number of menu interactions      | 4          |
| time_to_order   | FLOAT   | Time taken to place an order     | 11.5       |
| order_cancelled | INTEGER | Whether the order was cancelled  | 0          |
| order_value     | FLOAT   | Order value                      | 6.20       |



## 📊 Metrics

**Primary Metric**

* Order conversion rate

**Secondary Metric**

* Time to order

**Guardrail Metric**

* Cancellation rate



## 🔬 Hypothesis

**Null Hypothesis (H₀)**
Displaying a social-proof badge does not change order conversion rate.

**Alternative Hypothesis (H₁)**
Displaying a social-proof badge increases order conversion rate.


## ⚙️ Methodology

The experiment was analyzed using:

* Chi-square test to validate randomization balance
* Two-proportion z-test for conversion rate comparison
* Two-proportion z-test for cancellation rate comparison
* Effect size calculation to estimate business impact


## 📈 Results

* Conversion increased from **~20% (control)** to **~21% (treatment)**
* ~**1 percentage point lift (~5% relative improvement)**
* **Time-to-order decreased** in the treatment group
* **Cancellation rate difference was not statistically significant**
* Conversion test showed **statistically significant improvement (p < 0.05)**



## 💡 Conclusion

The A/B test results indicate that the **social-proof badge improves conversion performance** without negatively affecting order quality.

The **null hypothesis was rejected for conversion rate**, while **guardrail metrics showed no significant change**.

Recommendation: **Roll out the feature and continue monitoring cancellation rate post-launch.**
