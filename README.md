# Retail Customer Segmentation Using RFM Analysis

## Business Problem

A UK-based online retailer wants to improve customer retention with a limited marketing budget. The business needs to identify its most valuable customers, customers likely to stop buying, and the customer groups that should receive targeted retention campaigns.

## Objective

This project uses RFM analysis to segment customers based on:

- **Recency:** How recently a customer made a purchase
- **Frequency:** How many unique orders a customer made
- **Monetary:** How much a customer spent in total

The analysis supports marketing decisions for Champions, Loyal Customers, Potential Loyalists, At Risk Customers, and Lost Customers.

## Dataset

The analysis uses the Online Retail II transaction dataset from a UK-based online giftware retailer.

- Analysis period: December 2009 to December 2011
- Raw transaction rows: 1,067,371
- Currency: GBP (£)

## Tools Used

- Python
- pandas
- Jupyter Notebook
- Power BI

## Data Preparation

Before the RFM calculation, the analysis excludes:

- Rows without a customer ID
- Cancelled invoices beginning with `C`
- Zero or negative quantities
- Zero or negative prices

A sales field is calculated as:

`Sales = Quantity × Price`

## RFM Methodology

For each customer:

`Recency = analysis date − latest purchase date`

`Frequency = number of unique invoices`

`Monetary = total sales`

Each metric is scored from 1 to 5 using quintiles. The customer segmentation is based on the combined RFM behavior.

## Customer Segments and Suggested Actions

| Segment | Meaning | Suggested Action |
| --- | --- | --- |
| Champion | Recent, frequent, high-spending customers | VIP access, early product access, referral rewards |
| Loyal | Repeat customers with strong purchase behavior | Loyalty rewards, bundles, cross-selling |
| Potential Loyalist | Customers with potential to become repeat buyers | Second-purchase offers and recommendations |
| At Risk | Previously valuable customers who have not purchased recently | Personalized win-back campaign |
| Lost | Low-value customers inactive for a long time | Low-cost reactivation email only |

## Key Findings

| Segment | Customers | Revenue Share |
| --- | ---: | ---: |
| Champion | 1,292 | 68.12% |
| Loyal | 1,410 | 15.52% |
| At Risk | 1,074 | 11.13% |
| Potential Loyalist | 1,323 | 4.14% |
| Lost | 779 | 1.08% |

## Recommendation

1. Protect Champions through VIP experiences rather than large discounts.
2. Prioritize personalized win-back campaigns for At Risk customers.
3. Encourage Potential Loyalists to make a second purchase.
4. Use loyalty rewards and cross-selling for Loyal Customers.
5. Use low-cost campaigns only for Lost Customers.

## Project Files

- `rfm_customer_segmentation.ipynb` — pandas data cleaning, RFM scoring, and segmentation
- `customer_segments_using_rfm.csv` — final customer-level RFM output
- `segment_summary_rfm.csv` — segment-level business summary

## Limitation

The dataset has no campaign costs, response rates, discount costs, profit margins, or campaign-conversion data. Therefore, this analysis identifies retention priorities but does not calculate actual campaign ROI. Actual ROI should be validated through campaign tracking and A/B testing.
