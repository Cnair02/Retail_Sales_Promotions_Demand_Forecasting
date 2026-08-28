# Retail_Sales_Promotions_Demand_Forecasting

# Project Background

NorthStar Retail Group is a fictional multi-category retailer operating 50 stores and selling Grocery, Home, Clothing, Electronics, and Personal Care products.

The business regularly runs price promotions to increase demand, clear inventory, and attract customers. However, promotion success cannot be judged by sales volume alone. A discount may increase units sold while reducing gross profit enough to make the campaign unprofitable.

This project evaluates promotional performance using 2024 retail sales data containing store, product, date, category, price, promotion status, discount percentage, units sold, inventory level, and day-of-week fields. The analysis includes 2,800 records with 1,430 promoted observations and 1,370 non-promoted observations.

Business Questions
Do promotions create incremental sales, rather than simply sales that would have occurred anyway?

Which discount levels produce the strongest sales uplift?

Which product categories and stores respond best to promotions?

Are promotion-driven sales profitable after accounting for discount cost?

How should NorthStar Retail redesign its future promotional strategy?

The data cleaning and EDA has been performed with tools using Python, Pandas and Seaborn, Matplotlib libraries.

# Data Structure and Initial Checks

| Metric                   | Value                                 |
| ------------------------ | ------------------------------------- |
| Analysis period          | January 1 to December 31, 2024  |
| Total records            | 2,800                           |
| Stores                   | 50                              |
| Product categories       | 5                               |
| Promotion-active records | 1,430                           |
| Non-promotion records    | 1,370                           |
| Discount range           | 0% to 30%                       |
| Missing values           | None identified                 |

Prior to the beginning of the analysis, data cleaning and variety of checks were conducted for quality control and familiarization with the dataset.

## Assumptions
Because the dataset does not contain actual cost-of-goods-sold or campaign operating costs, the analysis applies a simplified financial assumption:

Cost price = 40% of listed selling price.

Unit profit = selling price minus assumed cost price.

Promotion cost = revenue multiplied by discount percentage.

Incremental ROI compares estimated incremental profit with discount cost.

These assumptions make the ROI analysis a portfolio demonstration rather than a fully audited financial result. In a production setting, actual landed cost, vendor funding, marketing cost, labour cost, and fulfilment cost should be included.

# Methodology
## Incrementality

Incrementality measures whether promotions generated additional demand beyond the expected baseline.

Incrementality % = (Average promoted units − Average non-promoted units) / Average non-promoted units × 100

Promoted observations averaged 27.60 units sold, compared with 24.92 units for non-promoted observations, yielding a 10.77% estimated sales lift

## Incremental ROI
The analysis used the following logic:

Incremental Profit = Promotional Profit − Baseline Profit
Incremental ROI = (Incremental Profit − Promotion Cost )/ Promotion Cost × 100

This emphasizes profitability rather than revenue or volume alone.

# Executive Summary

Promotions increased average sales from approximately 24.92 units without a promotion to 27.60 units during promoted periods—an incremental lift of 10.77%, or about 2.68 additional units per observation.

However, the commercial outcome was negative under the project’s cost assumptions. Total incremental profit was estimated at approximately 394,395, while total discount cost was approximately 8.38 million, resulting in an overall incremental ROI of -95.30%.

The key implication is that promotions successfully drive demand, but the discount depth and promotion design are not currently profit-efficient. NorthStar Retail should move from broad, high-discount campaigns toward targeted, controlled tests that prioritize incremental profit rather than sales volume alone.

## Insights gathered

1. Promotions Drive Incremental Demand
Promotions generated a 10.77% increase in average units sold, from roughly 24.92 to 27.60 units per observation.


This indicates that promotions are associated with additional demand. However, this estimate is descriptive because promotion assignment was not randomized and has not yet been adjusted for all possible confounding factors, such as product mix, store characteristics, seasonality, and inventory constraints.

2. Deep Discounts Produce More Volume
Sales uplift increased as discount depth increased. Higher discounts produced the strongest sales lift, but they did not generate better financial returns.


This demonstrates a key trade-off: demand response rises with discount depth, while profitability worsens.

4. Lower Discounts Have the Best ROI
All discount groups had negative incremental ROI under the project assumptions, but lower discounts were materially less unprofitable than deeper discounts.



The high-discount segment generated the largest unit-sales increase, but its estimated incremental profit was negative before accounting for discount cost, resulting in the weakest ROI

6. Grocery Shows the Strongest Category Response
Promotional responsiveness varied by category. Grocery showed the strongest estimated promotional lift, while Personal Care showed the weakest response.



This suggests promotions should not be deployed uniformly across the product portfolio. Categories with strong response can be prioritized for carefully designed price tests, while low-response categories may require alternative tactics such as bundles, loyalty offers, or improved merchandising.

7. Store Performance Is Highly Uneven
Promotional uplift varied substantially across the 50 stores. The best-performing stores achieved estimated sales lifts of approximately 46.20% and 43.58%, while several stores experienced negative lift, with the weakest store declining by approximately 10.18% during promotions.


This variation shows that blanket promotions are inefficient. Store-level targeting could reduce spend in locations where promotions do not create incremental demand.
  
## Recommendation

* Use Lower Discounts as the Default Test
Begin with low-discount campaigns rather than high-discount campaigns. Low discounts generated a positive sales lift of 4.38% while producing the least negative ROI of the three tested discount bands. Use larger discounts only when there is a specific strategic reason, such as inventory clearance, customer acquisition, a seasonal event, or vendor-funded promotions.
  
* Shift from Sales KPIs to Incremental Profit KPIs
Do not evaluate promotions based only on total revenue or units sold. Every campaign should report:
Incremental units sold
Incremental revenue
Incremental gross profit
Discount cost
Incremental ROI
Performance against a comparable non-promoted control group

  A campaign that creates sales volume but destroys margin should be redesigned or stopped.
  
* Target High-Response Categories
Prioritize controlled promotional tests in Grocery and Electronics, which showed the highest observed sales lift.
For Personal Care and other low-response segments, test non-price tactics first, including product bundles, personalized offers, loyalty points, cross-selling, or placement improvements.
Build a Store-Level Promotion Strategy
Create three store segments based on historical promotional lift:

  1. Scale: Stores with consistently high incremental lift and acceptable profit outcomes.

  2. Optimize: Stores with moderate lift where discount depth, product mix, or timing can be improved.

  3. Restrict: Stores with zero or negative promotional uplift.

For example, stores 27 and 46 were among the strongest performers, while several stores showed negative promotional lift.
  
* Introduce Holdout Testing
The current analysis compares promoted and non-promoted records, which is useful for exploratory analysis but does not prove causality. NorthStar Retail should assign comparable store-product groups into:

  Treatment group: Receives a promotion.

  Control group: Does not receive the promotion.

  This design will better distinguish true incremental sales from normal demand, seasonality, product popularity, or store-level differences.
  
# Business Impact
This analysis demonstrates that NorthStar Retail’s promotions increased unit demand by 10.77%, but the estimated overall incremental ROI was -95.30% after discount cost under the stated assumptions.

The recommended strategy is to reduce blanket discounting, begin with lower discount tiers, target responsive categories and stores, and validate each campaign through controlled testing. This would help the retailer protect margin while continuing to use promotions selectively to generate incremental demand.








