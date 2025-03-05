SQL Query Documentation: Supplier Performance Analysis

Overview

This SQL query extracts and calculates various performance metrics for suppliers based on order processing data. The data is sourced from the supplier_metrics (sm) and marketplace_product_info (mp) tables. The primary goal is to assess supplier performance based on order processing efficiency, cancellations, delays, and Service Level Agreement (SLA) compliance.

Tables Used

supplier_metrics (sm): Contains supplier-related data, including orders, cancellations, processing times, and other key performance indicators.

marketplace_product_info (mp): Provides additional product information, such as product categories.

Filters (WHERE Clause Parameters)

The query includes filters for:

representative: Supplier representative name.

city: The supplier's city location.

region: The supplier's regional location.

purchase_type: The type of purchase (Fresh or Grocery).

product_category: The category of the product supplied.

product_number: Unique identifier for the vendor’s product.

supplier_group_id: Identifier for the supplier group.

location_id: The branch identifier.

date_range: Date range for the data extraction.

Selected Columns & Their Meanings

Supplier Details:

Supplier Representative: The supplier's assigned representative.

Supplier City: The city where the supplier operates.

Supplier Region: The geographical region of the supplier.

Supplier Group ID: Unique identifier for the supplier group.

Supplier Group: Name of the supplier group.

Branch ID: Unique identifier for the branch location.

Branch: The supplier's branch name.

Product Category: The category of the supplied product.

Vendor Product Number: The product number assigned by the vendor.

Order Type: Type of purchase (e.g., Fresh, Grocery).

Supplier Performance Score Calculation:

A percentage score is calculated based on multiple performance factors, including processing rate, cancellation rate, pending orders, and SLA adherence.

The score is computed using conditional weightings:

Processing Rate: Orders processed vs. orders accepted.

Post-acceptance Cancellations: Rate of cancellations after acceptance.

Pending After Scan: Percentage of pending orders after scanning.

Returns: Ratio of returned orders to total orders.

SLA Compliance: Fresh and Grocery orders meeting SLA requirements.

Performance Metrics:

Processing Rate: Ratio of processed orders to accepted orders.

Cancelled After Acceptance: Total number of orders canceled after being accepted.

Pending After Scan: Total number of orders pending after scanning.

Returned Orders: Number of returned orders.

% Fresh Orders - SLA: Percentage of fresh orders meeting SLA.

% Grocery Orders - SLA: Percentage of grocery orders meeting SLA.

Additional Performance Metrics:

Total Orders: The total number of orders placed.

Accepted Orders: Orders that were accepted by suppliers.

Acceptance Rate: Ratio of accepted orders to total orders.

Total Processed Orders: The number of orders processed.

Cancelled After Dispatch: Orders canceled after being dispatched.

Not Scanned Orders: Orders that were not scanned.

Scanned Orders: Orders that have been scanned.

Delivered Orders: Successfully completed orders.

Reported Issues: Orders with reported issues.

Average Time to Accept: Average time taken to accept an order.

Average Time to Process: Average time taken to process an order.

Average Time to Deliver: Average time taken to complete an order.

Aggregations & Joins

The query joins supplier_metrics (sm) with marketplace_product_info (mp) on location_id to fetch relevant product information.

The data is aggregated using the GROUP BY clause, categorizing results by supplier representative, city, region, supplier group, and branch.

Various aggregate functions such as SUM(), COUNT(), and AVG() are used to calculate performance-related metrics.

Usage

This query is useful for supplier performance evaluation, identifying weak points in order processing, and improving logistics operations.

Businesses can use the calculated Supplier Performance Percentage to determine which suppliers meet expectations and which require improvement.

SLA compliance metrics help in assessing the efficiency of fresh and grocery order fulfillment.

Conclusion

This query provides a comprehensive analysis of supplier performance based on multiple criteria, offering valuable insights into operational efficiency. The metrics can help stakeholders make data-driven decisions to optimize supplier relationships and logistics processes.

