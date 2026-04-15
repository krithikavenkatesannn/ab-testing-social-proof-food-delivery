## 🔬 A/B Test: Impact of Social Proof Badge on Food Delivery Conversion


## 📌 Background & Objective

* Food delivery platforms offer endless choices, creating decision fatigue. Users browse longer and often leave without ordering. A social proof badge ("Popular" or "Most Ordered") was introduced to reduce uncertainty.
* **The objective:** does this badge increase orders without encouraging cancellations?



## 🧪 Experiment Design

A randomized controlled A/B test ran for 14 days across **88,708 users**.

| Parameter | Value |
|-----------|-------|
| Control | Standard listing without badge |
| Treatment | Listing with social-proof badge |
| Traffic Split | 50% / 50% |
| Randomization Unit | User-level |
| Sample Size | **88,708 users** |
| Duration | **14 days** |
| Randomization Check | SRM passed |



## 🗂️ Dataset Overview

Each row represents one user. Missing values in `time_to_order` and `order_value` occur for non-ordering users — expected.

| Column | Description |
|--------|-------------|
| user_id | Unique identifier |
| variant | control / treatment |
| ordered | 1 = placed order, 0 = no order |
| menu_clicks | Number of menu interactions |
| order_cancelled | 1 = cancelled after placement |
| time_to_order | Minutes from landing to order |
| order_value | Total order amount (₹) |
| user_type | new / returning |
| day_of_week | 0–6 |



## 📊 Executive Summary 

<br>
<p align="center">
  <img src="images/Screenshot 2026-04-06 123007.png" width="800"/>
</p>
<br>

* The social proof badge increased conversions. Users in the treatment group placed orders more often than those in the control group — **20.86%** versus **20.17%**. This is a **3.4%** relative increase, and the result is statistically significant (p = **0.0055**).

* Users exposed to the badge also spent more money. The average order value rose from **₹322** to **₹346**, a gain of **₹24** per order. This increase is statistically significant (p < **0.001**).
* They also decided faster. Time from opening the app to placing an order dropped from **13 minutes** to **12 minutes** (p < **0.001**).
* Importantly, the badge did not hurt order quality. Cancellation rates moved from **5.72%** in the control group to **6.30%** in the treatment group. While this is a slight increase, it is **not statistically significant** (p = **0.101**), meaning the data does not provide strong evidence that the badge caused more cancellations.
* **Business impact:** Over 14 days, the **₹24** AOV lift generated approximately **₹432,000** in incremental revenue from **18,000** orders. Projected monthly impact at full rollout is **₹925,000**.
* **Uncertainty note:** The 95% confidence interval for conversion lift is **[0.16pp, 1.22pp]**. The true effect could be as small as **0.16pp** — cautious optimism is warranted.


**Interactive Dashboard:** [View in Power BI](https://app.powerbi.com/view?r=eyJrIjoiZDE5OGZmOTQtY2Q4My00MzUxLWFjMDYtZTFjMDAzNTI3ZjI2IiwidCI6IjBiNmM1ZjE0LTFmOGEtNDYxNy04YzI4LTJiZTc5M2FmYzBjMCJ9)

## 🔍 Deep Dive: The Novelty Decay Finding


<br>
<p align="center">
  <img src="images/Screenshot 2026-04-06 122827.png" width="800"/>
</p>
<br>

* The treatment group outperformed control on **11 of 14 days**. But the most important finding is the decay pattern.

* **Week 1 lift: +0.99pp. Week 2 lift: +0.39pp.** That is a **61% erosion**. The badge works, but its effect is partially driven by novelty. Users habituate.
* **Spending behavior:** Users exposed to the badge spent more per order. Average order value increased by **₹24**, from **₹322** to **₹346**. This suggests the badge not only drives more orders but also encourages users to pick higher-value items.
* **Decision speed:** Users in the treatment group ordered faster. Time-to-order dropped from **13 minutes** to **12 minutes**. The badge helped users stop browsing and commit.
* **Exploration behavior:** Users in the treatment group clicked more menus — **8.59** interactions versus **7.64** in control. They did not decide faster because they saw less. They decided faster because they received clearer signals. More exploration, less hesitation.
* **User segments:** New users showed stronger lift than returning users. Social proof fills the information gap when users lack prior experience. Returning users still benefited, but less.




## 📏 Metrics Definition

**Primary — Conversion Rate:** The percentage of users who placed an order. Answers whether the badge increases order completion.

**Secondary — Average Order Value:** The average amount spent per order. Answers whether users spend more when influenced by social proof.

**Guardrail — Cancellation Rate:** The percentage of orders that were later cancelled. Ensures more orders do not mean worse orders.



## 🧪 Hypothesis

The null hypothesis stated that the social proof badge does not increase conversion rate. The alternative stated that it does. For the guardrail, the null stated that the badge does not change cancellation rate, while the alternative stated that it does.

## ⚙️ Methodology

A Chi-square SRM test confirmed balanced traffic allocation. A one-tailed proportion Z-test compared conversion rates. A two-tailed proportion Z-test evaluated cancellation rate differences. An independent two-sample T-test compared average order value between groups.



## 📈 Results

* **Conversion Rate (Primary Metric):** Users in the treatment group converted at **20.86%** compared to **20.17%** in control. This is a **0.69 percentage point** increase, or a **3.4%** relative lift. The result is statistically significant (p = **0.0055**). However, the 95% confidence interval **[0.16pp, 1.22pp]** means the true lift could be as low as **0.16pp**.

* **Cancellation Rate (Guardrail Metric):** Cancellations increased from **5.72%** in control to **6.30%** in treatment. This **0.58 percentage point** increase is **not statistically significant** (p = **0.101**). In plain language: the data does not give us strong evidence that the badge caused more cancellations.

* **Average Order Value (Secondary Metric):** Average order value climbed from **₹321.7** in control to **₹345.6** in treatment. This **₹23.9** increase is statistically significant (p < **0.001**). Users exposed to the badge spent more money per order.

* **Time to Order:** Users in the treatment group decided faster. Time dropped from **13.0 minutes** to **12.0 minutes** (p < **0.001**).

* **Menu Clicks:** Users in the treatment group clicked more menus — **8.59** versus **7.64** in control.



## ✅ Conclusion

The badge increases conversion and order value with no significant change in cancellations. However, the **61% novelty decay** from Week 1 to Week 2 is the critical finding. The effect is real but not permanent.
## 📌 Recommendation

**Conditional rollout approved.** Launch to **100%** of users with three conditions:

1. **Monitor weekly conversion lift for 4 weeks.** If decay continues beyond Week 2, reassess long-term value.

2. **Do not scale ad spend based on badge performance** until novelty effects stabilize.

3. **Run a follow-up experiment at week 8** testing alternative badge designs ("Trending" vs "Most Ordered") to re-establish a baseline.


