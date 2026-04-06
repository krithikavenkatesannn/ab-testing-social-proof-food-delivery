#  **A/B Test: Impact of Social Proof Badge on Food Delivery Conversion**

## 📌 **Background & Objective**

* Food delivery platforms typically offer users a wide variety of restaurants and menu options. While this increases choice, it can also introduce **decision fatigue**, causing users to spend more time browsing and ultimately drop off before completing an order. Users may hesitate due to uncertainty around **food quality, popularity, or trustworthiness**.

* To reduce drop-offs and improve decision confidence, a **social proof badge** (e.g., **"Popular", "Most Ordered", "Trending"**) was introduced to highlight trusted items and guide user choices.

**Objective:**  

*  The primary goal of this experiment is to evaluate whether displaying a **social-proof badge increases order conversion rate** while ensuring **no negative impact on order quality metrics such as cancellations**.





<br>

<p align="center">
  <img src="images/Screenshot 2026-04-06 123007.png" width="800"/>
</p>

<br>



## 🧪 **Experiment Design**

A **randomized controlled A/B experiment** was conducted to evaluate the impact of introducing a social-proof badge.

* **Experiment Type:** Randomized controlled A/B test  
* **Variants:**  
  * **Control →** Standard food listing without social-proof badge  
  * **Treatment →** Food listing with social-proof badge  
* **Traffic Split:** **50% Control / 50% Treatment**  
* **Unit of Randomization:** **User-level randomization**  
* **Unit of Analysis:** **User session (whether user placed an order)**  
* **Sample Size:** **88,708 users**  
* **Duration:** **14 days continuous run**  
* **Randomization Check:** **Sample Ratio Mismatch (SRM) test** performed to validate balanced traffic allocation  

The experiment ensured both groups were exposed simultaneously to **control for day-of-week effects and behavioral bias**.



## 🗂️ **Dataset Overview**

The dataset contains **user-level interaction data** collected during the A/B experiment. Each row represents a user exposed to either the **control or treatment variant** during the experiment period.

**Total Records:** **88,708 users**  
**Granularity:** **User-level observations**  
**Time Period:** **14-day experiment window**

### 📖 **Data Dictionary**

| Column | Description |
|--------|-------------|
| user_id | Unique identifier for each user |
| date | Date of user session |
| variant | Experiment group (control / treatment) |
| ordered | Binary indicator (1 = user placed order, 0 = no order) |
| menu_clicks | Number of menu interactions before exit/order |
| order_cancelled | Binary indicator (1 = order cancelled after placement) |
| time_to_order | Time taken (minutes) from landing to order completion |
| order_value | Total order amount in ₹ |
| user_type | User segment (new / returning) |
| day_of_week | Numeric day indicator (0–6) for weekday analysis |

Missing values in **time_to_order** and **order_value** occur for users who **did not place an order** and are therefore expected.



## 📏 **Metrics Definition**

### 🎯 **Primary Metric — Conversion Rate**

**Percentage of users who placed an order** after being exposed to the variant.  
This metric directly measures whether the **social-proof badge increases order completion**.

### 💰 **Secondary Metric — Average Order Value (AOV)**

**Average order amount among users who placed an order.**  
This metric evaluates whether users **spend more when influenced by social proof**.

### 🛡️ **Guardrail Metric — Cancellation Rate**

**Percentage of placed orders that were later cancelled.**  
This metric ensures **increased conversions do not come at the cost of lower-quality or impulsive orders**.



## **Hypothesis**

**Null Hypothesis (H₀):**  
Displaying the **social-proof badge does not increase the conversion rate** compared to the control group.

**Alternative Hypothesis (H₁):**  
Displaying the **social-proof badge increases the conversion rate** compared to the control group.

**Guardrail Null Hypothesis (H₀):**  
Displaying the social-proof badge **does not change the cancellation rate**.

**Guardrail Alternative Hypothesis (H₁):**  
Displaying the social-proof badge **changes the cancellation rate**.

## ⚙️ **Methodology**

### 🔍 **Randomization Balance Check**

A **Chi-square test** was performed to detect **Sample Ratio Mismatch (SRM)** and confirm equal traffic allocation.

### 📈 **Primary Metric Analysis**

A **Proportion Z-test (one-tailed)** was used to compare conversion rates between control and treatment groups.

### 🛡️ **Guardrail Metric Analysis**

A **Proportion Z-test (two-tailed)** was used to evaluate differences in cancellation rate.

### 💰 **Secondary Metric Analysis**

An **Independent two-sample T-test** was used to compare **average order value** between groups.



## **Results**
<br>
<p align="center">
  <img src="images/Screenshot 2026-04-06 122827.png" width="800"/>
</p>
<br>

### **Conversion Rate**

* The treatment group showed a **higher conversion rate (20.86%)** compared to the control group **(20.17%)**, resulting in a **+0.69 percentage point lift** (**+3.42% relative increase**).  
The **Proportion Z-test indicated that this improvement was statistically significant (p = 0.0055)**.

### **Cancellation Rate**

* The cancellation rate increased slightly from **5.72% (control)** to **6.30% (treatment)**.  
However, the difference was **not statistically significant (p = 0.101)**, indicating **no strong evidence of degraded order quality**.

### **Average Order Value**

* Average order value increased from **₹321.7 (control)** to **₹345.6 (treatment)**.  
The **independent T-test showed this increase was statistically significant (p < 0.001)**, suggesting users **spent more when exposed to social proof**.



##  **Conclusion**

* The introduction of the **social-proof badge led to a statistically significant increase in conversion rate and average order value**, while the **cancellation rate did not show a significant change**.
* These findings suggest that **social proof effectively reduces decision friction and encourages users to place higher-value orders without negatively impacting order quality**.



##  **Recommendation**

* It is recommended to **roll out the social-proof badge to 100% of users**. Since **novelty analysis indicated a slight decline in lift over time**, performance should be **monitored post-launch to ensure sustained impact**.
*  Further experiments can also be conducted to **optimize badge placement, messaging, and personalization** to maximize **long-term business value**.

