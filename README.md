# Coffee Shop Sales Analysis (Excel)

An Excel project that analyses six months of sales (Jan - Jun 2023) from three coffee-shop stores in New York City: **Astoria, Hell's Kitchen and Lower Manhattan**.

<img width="1722" height="718" alt="image" src="https://github.com/user-attachments/assets/3591c89f-445f-4837-8801-ec4aa9ce3122" />


## Business questions

- How does revenue change month by month, and do all stores follow the same pattern?
- Which product categories and products earn the most?
- At what hours and on which weekdays are sales highest?
- How do the three stores compare?

## Dataset

| Item | Detail |
|---|---|
| Source | Coffee Shop Sales transactions (Maven Analytics sample dataset) |
| Period | 01 Jan 2023 - 30 Jun 2023 (181 days) |
| Size | 149,116 transaction rows |
| Key fields | transaction_date, transaction_time, transaction_qty, store_location, product_category, product_type, product_detail, unit_price |

## Data preparation

1. **Transactions** sheet holds the raw data (unchanged).
2. **Query** sheet is the cleaned data from Power Query: the size (Small / Regular / Large) is split from `product_detail` into a `Size` column ("Not Defined" for items without size).
3. Removed trailing spaces in `product_detail`; formatted date and time columns.
4. Data checks: no blanks, no duplicate `transaction_id`, Query and Transactions match row by row.
5. Added helper columns (formulas): `Revenue = transaction_qty x unit_price`, `Month`, `Weekday`, `Hour`.

## Workbook structure

| Sheet | Content |
|---|---|
| Dashboard | KPI cards, 6 charts and key insights |
| Analysis | 8 formula-driven tables (SUMIFS / COUNTIFS): month x store, category, product type, hour, weekday, size, store summary, top 10 products |
| Query | Cleaned data + helper columns |
| Transactions | Raw data |
| Project Notes | Objective, cleaning steps and assumptions |

## Key results

| Metric | Value |
|---|---|
| Total revenue | $698,812 |
| Total orders | 149,116 |
| Units sold | 214,470 |
| Average order value | $4.69 |
| Average daily revenue | $3,861 |

- **Revenue more than doubled** from $81.7K (Jan) to $166.5K (Jun). February was the only month that fell.
- **Coffee (38.6%) and Tea (28.1%)** bring about two-thirds of revenue. Barista Espresso is the top product type ($91.4K).
- **Morning rush:** 8-10 AM gives 37% of revenue; 10 AM is the busiest hour. Sales are flat (~$40K per hour) from 11 AM to 5 PM.
- **Weekdays are almost equal** ($96.9K - $101.7K), so the opportunity is in hours, not days.
- **Stores are close:** Hell's Kitchen leads by only 2.8% over Lower Manhattan, which has the highest average order value ($4.81).
- **Small-size drinks** give only 6.6% of revenue.

![Monthly revenue](images/01_monthly_revenue.png)
![Hourly revenue](images/03_hourly_revenue.png)

## Recommendations

1. Staff and stock for the 8-10 AM rush.
2. Test a mid-day offer (for example a bakery + drink combo) to lift the flat afternoon.
3. Focus range and promotions on Coffee and Tea.
4. Review whether staying open in the last hour (8 PM, ~0.4% of revenue) is worth the cost.
5. Encourage Regular / Large sizes through menu design and upsell prompts.

## Limitations

- Only six months of data, so seasonality and year-on-year growth cannot be measured.
- No cost data, so the analysis is about revenue, not profit.
- No order id, so each transaction row is treated as one order.

## Files

- `Coffee_Shop_Sales_PROJECT_Completed.xlsx` - the Excel project
- `Coffee_Shop_Sales_Report.pdf` - full written report
- `images/` - charts used in this README

## Tools

Microsoft Excel (Power Query, SUMIFS / COUNTIFS / INDEX-MATCH, charts), Python (data checks, report charts).

---
*Author: Sagun Tripathi*
