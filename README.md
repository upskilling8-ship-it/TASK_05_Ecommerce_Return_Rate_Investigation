# TASK_05_Ecommerce_Return_Rate_Investigation
Analysis of e-commerce product return rates and associated factors.
# TASK 05 - E-commerce Return Rate Investigation

## 1. Problem Statement

Product returns are an important challenge in e-commerce because they can increase operational costs, shipping expenses, inventory handling, and customer service workload.

The objective of this project is to investigate return patterns in an e-commerce dataset and identify factors that may be associated with higher return rates.

The analysis focuses on:

* Category vs Return Rate
* Price vs Return Rate
* Shipping Cost vs Return Rate
* Discount vs Return Rate
* Outlier detection
* Statistical hypothesis testing
* Behavioral segmentation
* Business recommendations

---

## 2. Dataset Description

The dataset used for this project is:

**`diversified_ecommerce_dataset.csv`**

The dataset contains approximately **1,000,000 records** and includes product, customer, pricing, shipping, and return-related information.

### Important Columns

| Column             | Description                            |
| ------------------ | -------------------------------------- |
| Product ID         | Unique identifier for a product        |
| Product Name       | Name of the product                    |
| Category           | Product category                       |
| Price              | Product price                          |
| Discount           | Discount percentage                    |
| Tax Rate           | Applicable tax rate                    |
| Stock Level        | Available stock quantity               |
| Customer Age Group | Customer age category                  |
| Customer Location  | Customer location                      |
| Customer Gender    | Customer gender                        |
| Shipping Cost      | Cost of shipping                       |
| Shipping Method    | Method used for delivery               |
| Return Rate        | Return rate associated with the record |
| Seasonality        | Seasonal information                   |
| Popularity Index   | Product popularity measure             |

### Dataset Limitations

The dataset does not contain:

* Customer ID
* Delivery Time
* Return Reason

Therefore, individual customer return frequency and the effect of delayed delivery could not be directly analyzed.

---

## 3. Statistical Methods

The following methods were used during the investigation.

### Descriptive Analysis

Average Return Rate was calculated across:

* Product categories
* Price groups
* Shipping Cost groups
* Discount groups

Continuous variables were grouped into ranges where necessary to make the comparisons easier to interpret.

### Outlier Analysis

The **Interquartile Range (IQR)** method was used to identify statistical outliers.

The standard rule of:

**Lower Bound = Q1 - 1.5 × IQR**

**Upper Bound = Q3 + 1.5 × IQR**

was applied to:

* Return Rate
* Price
* Shipping Cost
* Discount

### Hypothesis Testing

A **One-Way ANOVA** test was performed to determine whether average Return Rate differed significantly across the five Discount Groups.

#### Hypotheses

**H₀:** Discount level has no significant effect on return rate.

**H₁:** Discount level has a significant effect on return rate.

A significance level of **0.05** was used.

### Segmentation

Transaction-level behavioral segments were created using median-based thresholds:

* High-return vs Lower-return
* Discount-driven vs Lower-discount
* Premium vs Lower-price

Because there is no Customer ID, these segments represent **transaction-level behavior rather than individual customers**.

---

## 4. Return Findings

### Category Findings

Footwear had the highest average return rate:

| Category        | Average Return Rate |
| --------------- | ------------------: |
| Footwear        |              10.51% |
| Home Appliances |              10.50% |
| Electronics     |              10.49% |
| Books           |              10.48% |
| Apparel         |              10.48% |

The differences between categories were very small.

### Price Findings

| Price Group | Average Return Rate |
| ----------- | ------------------: |
| 10–500      |              10.49% |
| 501–1000    |              10.50% |
| 1001–1500   |              10.49% |
| 1501–2000   |              10.49% |

Return rates remained almost identical across price groups.

### Shipping Cost Findings

| Shipping Cost Group | Average Return Rate |
| ------------------- | ------------------: |
| 0–10                |              10.50% |
| 11–20               |              10.49% |
| 21–30               |              10.50% |
| 31–40               |              10.47% |
| 41–50               |              10.50% |

Shipping cost showed only small differences in return rate.

### Discount Findings

| Discount Group | Average Return Rate |
| -------------- | ------------------: |
| 0–5%           |              10.49% |
| 6–10%          |              10.48% |
| 11–15%         |              10.50% |
| 16–20%         |              10.50% |
| 21–25%         |              10.49% |

Higher discounts did not show a clear increase in return rates.

### ANOVA Result

The One-Way ANOVA produced:

* **F-statistic:** 0.3630
* **p-value:** 0.8351
* **Significance level:** 0.05

Since the p-value is greater than 0.05, there is no statistically significant evidence that the discount groups have different average return rates.

### Outlier Findings

No statistical outliers were detected for:

* Return Rate
* Price
* Shipping Cost
* Discount

using the standard 1.5 × IQR method.

---

## 5. Visual Insights

Bar charts were used to visualize the main return-rate comparisons.

### Average Return Rate by Category

The category analysis showed that Footwear had the highest average return rate, at approximately 10.51%. However, all categories had very similar return rates.

### Average Return Rate by Price Group

The price-group bar chart showed almost no variation in average return rates across different price ranges.

### Average Return Rate by Shipping Cost Group

The shipping-cost analysis showed only minor differences between groups. The 41–50 shipping-cost group had the highest average return rate, while the 31–40 group had the lowest.

### Average Return Rate by Discount Group

The discount bar chart showed that the highest discount group did not have the highest return rate. This supports the conclusion that higher discounts do not show a clear association with higher returns in this dataset.

### Outlier Visualizations

Box plots were created for:

* Return Rate
* Price
* Shipping Cost
* Discount

The box plots did not identify statistical outliers using the IQR method.

---

## 6. Recommendations

Based on the analysis, the following business recommendations are proposed:

### 1. Monitor category-level returns

Operations teams should regularly monitor return rates by category, particularly Footwear, which had the highest observed average return rate.

### 2. Investigate product-level return patterns

Return rates should also be analyzed by individual Product ID to identify products with consistently higher return rates.

### 3. Collect return reasons

Future data collection should include standardized return reasons such as:

* Product quality issue
* Wrong size
* Damaged product
* Incorrect product
* Product not as expected
* Late delivery
* Customer changed their mind

### 4. Do not reduce discounts solely to control returns

The statistical analysis did not find a significant difference in return rates across discount groups. Therefore, discount reductions should not be used as a return-reduction strategy based on this analysis alone.

### 5. Track delivery performance

Delivery Time should be added to future datasets so that the relationship between delivery delays and returns can be investigated.

### 6. Introduce Customer ID

A Customer ID would allow the business to identify customers with repeated or unusually high return frequency.

### 7. Develop a return monitoring dashboard

A dashboard could monitor:

* Overall Return Rate
* Return Rate by Category
* Return Rate by Product
* Return Rate by Discount
* Return Rate by Price
* Return Rate by Shipping Method
* Return Reasons
* Delivery Delays
* Customer Return Frequency

---

## 7. Future Scope

The current investigation can be expanded with additional data and analytical techniques.

### Customer-Level Analysis

Adding Customer ID would allow analysis of:

* Frequent returners
* High-value returners
* Customer return frequency
* Customer lifetime behavior

### Delivery Analysis

Adding expected and actual delivery dates would allow calculation of delivery delays and investigation of whether delayed deliveries are associated with higher returns.

### Return Reason Analysis

Adding return reasons would help identify the actual operational causes behind returns.

### Product-Level Analysis

Future analysis can identify individual products with unusually high return rates and investigate their characteristics.

### Advanced Statistical Analysis

Future work could include:

* Correlation analysis
* Logistic regression
* Chi-square tests
* Multiple regression
* Predictive modeling
* Machine learning classification

These methods could help identify combinations of factors associated with higher return probability.

### Dashboard Development

The final analysis could be converted into an interactive dashboard using tools such as Power BI, Tableau, or Python-based dashboard frameworks.

---

## Conclusion

The analysis found that the average return rate remains close to **10.5%** across categories, price groups, shipping-cost groups, and discount groups.

Footwear recorded the highest category-level average return rate at approximately **10.51%**, but the difference between categories was small.

The One-Way ANOVA test produced a **p-value of 0.8351**, indicating no statistically significant difference in average return rates across discount groups.

Overall, the current dataset does not identify a strong single factor driving returns. Adding **Customer ID, Delivery Time, and Return Reason** data would allow a deeper investigation and provide more actionable insights for reducing e-commerce returns.
