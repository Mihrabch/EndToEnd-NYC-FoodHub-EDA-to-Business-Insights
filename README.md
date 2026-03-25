# NYC Restaurant Data Analysis

## Context
The number of restaurants in New York is increasing day by day. Lots of students and busy professionals rely on those restaurants due to their hectic lifestyles. Online food delivery service is a great option for them. It provides them with good food from their favorite restaurants. A food aggregator company FoodHub offers access to multiple restaurants through a single smartphone app.

The app allows the restaurants to receive a direct online order from a customer. The app assigns a delivery person from the company to pick up the order after it is confirmed by the restaurant. The delivery person then uses the map to reach the restaurant and waits for the food package. Once the food package is handed over to the delivery person, he/she confirms the pick-up in the app and travels to the customer's location to deliver the food. The delivery person confirms the drop-off in the app after delivering the food package to the customer. The customer can rate the order in the app. The food aggregator earns money by collecting a fixed margin of the delivery order from the restaurants.

## Objective
The food aggregator company has stored the data of the different orders made by the registered customers in their online portal. They want to analyze the data to get a fair idea about the demand of different restaurants which will help them in enhancing their customer experience. Suppose you are hired as a Data Scientist in this company and the Data Science team has shared some of the key questions that need to be answered. Perform the data analysis to find answers to these questions that will help the company to improve the business.

---

## Data Description
The data contains the different data related to a food order.
1. **Source:** FoodHub internal order portal
2. **Size:** 1,898 orders · 9 features
   
## Data Dictionary
1. **Order_id**: Unique ID of the order
2. **Customer_id**: ID of the customer who ordered the food
3. **Restaurant_name**: Name of the restaurant
4. **Cuisine_type**: Cuisine ordered by the customer
5. **Cost_of_the_order**: Cost of the order
6. **Day_of_the_week**: Indicates whether the order is placed on a weekday or weekend (The weekday is from Monday to Friday and the weekend is Saturday and Sunday)
7. **Rating**: Rating given by the customer out of 5
8. **Food_preparation_time**: Time (in minutes) taken by the restaurant to prepare the food. This is calculated by taking the difference between the timestamps of the restaurant's order confirmation and the delivery person's pick-up confirmation.
9. **Delivery_time**: Time (in minutes) taken by the delivery person to deliver the food package. This is calculated by taking the difference between the timestamps of the delivery person's pick-up confirmation and drop-off information.

---

## Approach

1. **Data Profiling** — shape, types, missing values, statistical summary
2. **Univariate Analysis** — distributions of cost, rating, cuisine, time variables
3. **Multivariate Analysis** — cuisine vs cost/prep time, rating vs operational metrics, correlation heatmap
4. **Business Q&A** — eight targeted questions answered with supporting analysis
5. **Conclusions & Recommendations** — actionable insights for the business

---

## Key Findings

| # | Finding | Detail |
|---|---------|--------|
| 1 | **Top cuisine** | American leads at 30.8%, followed by Japanese (24.8%) and Italian (15.7%) — these three account for ~71% of all orders |
| 2 | **Rating gap** | 38.8% of orders go unrated, limiting the platform's ability to surface quality signals |
| 3 | **Weekend demand** | Weekend order volume is ~2× weekday, but mean delivery time is ~6 min longer, indicating a capacity gap |
| 4 | **60-min breaches** | 10.5% of orders exceed 60 minutes end-to-end (prep + delivery) |
| 5 | **High-value orders** | 29.2% of orders exceed $20, triggering the higher 25% commission tier |
| 6 | **Cuisine pricing** | Southern cuisine commands the highest prices; Korean and Vietnamese are the most affordable |
| 7 | **Prep time** | Thai cuisine has the longest preparation time; Korean is the quickest — consistent across weekdays and weekends |
| 8 | **Quality signal** | Higher-rated orders correlate with higher cost and longer delivery times — customers trade speed for quality |
| 9 | **Promo-eligible** | Shake Shack, The Meatball Shop, Blue Ribbon Sushi, and Blue Ribbon Fried Chicken meet criteria (rating count > 50, avg rating ≥ 4) |

---

## Conclusions

1. **Demand is cuisine-concentrated** — American, Japanese, Italian, and Chinese cuisines drive ~82% of all orders. Patterns are stable across weekdays and weekends.
2. **Operational bottleneck on weekends** — demand doubles on weekends but delivery capacity does not scale proportionally, resulting in longer delivery times.
3. **Customers value quality over speed** — higher ratings correlate with longer delivery times and higher costs, suggesting the customer base prioritises food quality.
4. **Pricing varies meaningfully by cuisine** — Southern cuisine is the most expensive while Korean and Vietnamese are the cheapest, offering price-sensitive targeting opportunities.
5. **Preparation times are operationally stable** — minimal variation across cuisines on weekdays vs. weekends simplifies kitchen planning.

---

## Recommendations

| Priority | Area | Recommendation |
|----------|------|----------------|
| 🔴 High | Ratings | Send post-delivery in-app nudges to reduce the 38.8% unrated gap — improved coverage strengthens the recommendation engine |
| 🔴 High | Weekend capacity | Investigate delivery staffing on weekends — demand doubles but delivery times worsen by ~6 min |
| 🟡 Medium | Delivery SLA | Flag orders at risk of exceeding 60 min at placement using prep time estimates so customers can set expectations proactively |
| 🟡 Medium | Promotions | Extend promotional offers to mid-tier cuisines (Mexican, Indian) and highlight affordable options (Korean, Vietnamese) to diversify demand |
| 🟡 Medium | Efficiency | Streamline preparation for time-intensive cuisines like Thai; promote quick-prep options during peak hours |
| 🟢 Low | Pricing | Explore dynamic weekend pricing for high-demand cuisines to improve margin without impacting volume |

---

## Repository Structure

```
├── foodhub_order.csv            # Dataset
├── NYC_FoodHub_Analysis.ipynb   # End-to-end analysis notebook
└── README.md
```

---

## Stack

`Python` `Pandas` `NumPy` `Matplotlib` `Seaborn`
