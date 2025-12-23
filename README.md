# 🛒 E-commerce User Behavior Deep Dive Analysis: Strategy Optimization & Bottleneck Diagnosis

## 🚀 Project Overview

Based on real user behavior data from an e-commerce platform (Taobao), this project aims to diagnose user behavior patterns and conversion churn bottlenecks through in-depth, multi-dimensional data analysis. It provides data-driven strategic recommendations for refined operations, product recommendation, and user value maintenance.

* **Data Source:** Alibaba Tianchi Dataset (User Behavior Data) **[https://tianchi.aliyun.com/dataset/649](https://tianchi.aliyun.com/dataset/649)**
* **Analysis Goal:** Optimize user experience and improve overall platform conversion efficiency and user loyalty.
* **Analysis Framework:** Centered around five core business questions regarding the user lifecycle, transaction efficiency, and product value.

## 🛠️ Methodology & Data Prep

### 1. Methodology

| Domain | Tools/Tech | Purpose |
| :--- | :--- | :--- |
| **Data Processing & Modeling** | Python (Pandas), SQL | Data cleaning, feature engineering, RFM model construction |
| **Data Storage** | SQL/SQLite | Structured data querying and aggregation calculations |
| **Visualization** | Tableau, Matplotlib | Creating retention curves, hourly trend charts, RFM segmentation & strategic positioning matrices |

### 2. Data Cleaning & Normalization

1.  **Time Window Confirmation:** Excluded extreme timestamp outliers (e.g., the years 1902, 2027) and strictly limited the analysis range to **2017-11-25 to 2017-12-03** to ensure validity.
2.  **Behavior Classification:** Merged `fav` (favorite) and `cart` (add-to-cart) into **"Interest Behaviors"**, simplifying the conversion funnel to focus on the decision-making process from interest to purchase.

## 🧠 Key Analysis & Findings

### Q1: User Retention & Lifecycle Analysis

* **Conclusion:** During the analysis period, **existing users accounted for 99.97%**, indicating that during the "Double 12" warm-up phase, the platform's **attraction for new users was severely insufficient**, and acquisition efforts were ineffective.
* **Recommendation:** Urgently adjust marketing budgets and strategies to launch heavy, exclusive **first-order incentives** for new users, focusing on solving the user acquisition problem.

### Q2: Conversion Funnel Analysis (Macro Churn Diagnosis)

* **Goal:** Identify the maximum churn points from browsing to purchasing.
* **Key Chart:** Conversion Funnel ([funnel_chart.png](Problem 2.png)

| Funnel Stage | Conversion Rate | Diagnosis & Focus |
| :--- | :--- | :--- |
| **PV $\to$ Interest Behavior** (Fav/Cart) | 9.39% | Moderate performance; users show initial interest in products. |
| **Interest Behavior $\to$ Purchase (Buy)** | **2.26%** | **Severe Churn Bottleneck**: Over 97% of users abandon items they favorited/added to cart. The problem is concentrated in the "final kick" decision stage. |

* **Operational Recommendations (Fixing Churn):**
    * **Cart Recall:** Push **limited-time coupons** or **shipping fee waivers** to users with items remaining in the cart for over 24-48 hours to break price hesitation.
    * **Checkout Trust:** Highlight **shipping transparency**, **delivery time**, and **payment security guarantees** on the checkout page to boost user confidence.

### Q3: Hourly Traffic vs. Efficiency Analysis

* **Goal:** Distinguish between traffic scale and purchase efficiency to guide precise resource allocation.
* **Key Chart:** Hourly Trends ([hourly_trends.png](Problem 3.png))

| Time Period | Metric | Findings | Operational Strategy |
| :--- | :--- | :--- | :--- |
| **Morning (10:00)** | **Conversion Efficiency (CR)** | Conversion rate hits its **peak**; user purchase intent is strongest. | **🎯 Focus on Conversion:** Promote high-value, high-margin products with conversion as the core goal. |
| **Evening (21:00)** | **Traffic (PV)** | Traffic hits its **peak**, but conversion efficiency drops sharply. | **📢 Guide Interest:** Avoid consuming high-value promotional resources here; shift focus to **brand exposure** and **guiding users to add-to-cart/favorite**. |

### Q4: RFM User Value Segmentation Analysis

* **Goal:** Segment users based on value to formulate differentiated marketing strategies.
* **Method:** Adopted the **R-F Model** (Recency-Frequency) to divide users into 6 major groups.
* **Key Chart:** RFM Treemap ([RFM_segmentation.png](Problem 4.png))

| RFM Group | Share | Core Characteristics | Marketing Strategy |
| :--- | :--- | :--- | :--- |
| **Key Value Users** | 20.19% | Recent purchases, high frequency. | **Reward/Retain:** Provide VIP exclusive services or early access to events to solidify loyalty. |
| **Low Value/Churn Customers** | 25.07% | Long purchase gap, low frequency. | **Reactivate/Recall:** Stimulate repurchases through low-threshold coupons or **targeted product recommendations**. |
| **Potential/New Users** | 14.48% | Recent purchases, low frequency. | **Accelerate Conversion:** Push new user gift packs and cross-sell to convert them into loyal customers. |

### Q5: Product Category Performance Analysis (Strategic Matrix)

* **Goal:** Evaluate product category scale, potential (repurchase frequency), and efficiency (conversion rate).

| Category ID | Conversion Rate (%) | Purchase Frequency (Potential) | Strategic Positioning |
| :--- | :--- | :--- | :--- |
| **2885642, 1464116** | $\approx 18\%$ | Medium | **🥇 Golden Categories**: High efficiency; investment should be increased to use these as **main drivers for user acquisition**. |
