**Finance and Sales Analytics**  

## Overview  
This database provides a unified system for **sales and financial analytics**, integrating data from customers, products, markets, costs, and sales. It offers optimized reporting through **pre-computed views, stored procedures, and window functions** to track performance and generate insights efficiently.  


## **Schema Overview**  

### **Fact Tables**  
- **fact_sales_monthly**: Monthly sales data by product and customer.  
- **fact_gross_price**: Product prices by fiscal year.  
- **fact_pre_invoice_deductions**: Discounts before invoicing.  
- **fact_post_invoice_deductions**: Deductions after invoicing.  
- **fact_freight_cost**: Freight and shipping costs.  
- **fact_manufacturing_cost**: Product manufacturing costs.  
- **fact_forecast_monthly**: Sales forecasts.

### **Dimension Tables**  
- **dim_customer**: Customer details (market, region).  
- **dim_product**: Product and variant details.  
- **dim_date**: Calendar and fiscal year data for time-based joins.


## **Key Modules & Use Cases**  

1. **Sales Analytics**  
   - **Top Markets & Customers**: Identify top-performing markets and customers by net sales.  
   - **Product Performance**: Fetch top products per division by sales quantity.  
   - **Net Sales Reporting**: Use views (e.g., `net_sales`) to generate reports with all deductions applied.  

2. **Finance Analytics**  
   - **Cost Analysis**: Track freight, manufacturing, and operational expenses using relevant fact tables.  
   - **Expense Distribution**: Calculate the percentage contribution of expenses by category or region.  


## **Performance Optimizations**  
- **Avoided Function Calls**: Replaced `get_fiscal_year()` with direct joins on `dim_date`.  
- **Fiscal Year in Sales Table**: Added `fiscal_year` to **fact_sales_monthly** to reduce unnecessary joins.  
- **Pre-computed Views**: Used views like `sales_preinv_discount` and `sales_postinv_discount` to streamline reporting.


## **Stored Procedures**  
- **`get_top_n_markets_by_net_sales`**: Fetches top N markets by net sales for a given year.  
- **`get_top_n_customers_by_net_sales`**: Identifies top N customers by market and fiscal year.  
- **`get_top_n_products_per_division_by_qty_sold`**: Retrieves top N products from each division by quantity sold.


## **Advanced Analytics Using Window Functions**  
- **Expense Share Analysis**: Calculate each expense’s contribution to the total.  
- **Cumulative Expense Tracking**: Monitor total expenses over time.  
- **Regional Sales Share**: Analyze customer-wise sales contribution by region.

## **Usage Instructions**
1. **Clone the repository:**
2. **Set up the database:**
3. **Execute SQL Queries:**

## **Contributors and Maintainers**
**Project Maintainer**: Simarpreet Chawla (simarchawla767@gmail.com)
**Contributors**: Open for contributions! Feel free to submit pull requests or open issues for discussions on improvements.





