# Comprehensive Case Study: Fraud Analysis for B2B E-Commerce Platform

## Problem Statement

ABC Company, a B2B e-commerce platform, processes thousands of daily orders and partners with several courier companies for delivery. The courier charges depend on shipment weight, delivery distance, and type of shipment. The company identified discrepancies in courier billing and initiated an analysis to:

1.  Compare order weight and delivery zones reported by courier companies with ABC’s internal data.
2.  Calculate expected courier fees based on ABC’s rate card.
3.  Identify cases of overcharging and undercharging.
4.  Provide insights to optimize operations and reduce costs.

### Data Sources

1.  **Website Order Report**: Contains order IDs and product SKUs.
2.  **SKU Master**: Includes the gross weight of products.
3.  **Courier Company Invoices**: Includes AWB numbers, shipment weight, delivery zones, and billed amounts.
4.  **Warehouse PIN Mapping**: Links warehouse PINs to delivery areas.
5.  **Courier Rate Card**: Details fixed and additional charges by weight slab, delivery area, and shipment type.

* * *

## Methodology

The analysis was conducted in multiple steps to ensure comprehensive coverage of all discrepancies.

### Step 1: Data Cleaning and Preparation

*   Imported and consolidated all datasets using **Power Query**.
*   Standardized column names and formats.
*   Removed duplicates and addressed missing values.

### Step 2: Calculations and Derivations

**Key Calculations:**

1.  **Total Order Weight**:
    
    *   Sum of product weights (from SKU Master) for each order.
    *   Rounded up to the nearest 0.5 kg.
    *   Formula: `=CEILING(SUM(SKU_Weights), 0.5)`
2.  **Expected Charges**:
    
    *   Based on ABC’s rate card: Fixed charge + Additional charges (by weight slab).
    *   Implemented using **SWITCH** in Excel and **DAX calculated columns** in Power BI.
3.  **Weight Slabs and Zones**:
    
    *   Categorized weights into slabs using **VLOOKUP** and **SWITCH**.
    *   Zones determined using PIN mapping data.
4.  **Billing Comparisons**:
    
    *   Difference between expected charges and billed amounts.
    *   Categorized into "Correctly Charged," "Overcharged," or "Undercharged" using **nested IF statements**.

### Step 3: Visualization and Summary

*   Designed summary tables and charts for insights.
*   Created interactive dashboards in **Power BI** with slicers for detailed exploration.

* * *

## Analysis and Insights

### Summary Table

| Description | Count | Amount (Rs.) |
| --- | --- | --- |
| Total Orders where ABC was Correctly Charged | 9 | 383.8 |
| Total Orders where ABC was Overcharged | 94 | 11,100.3 |
| Total Orders where ABC was Undercharged | 4 | 274.7 |

### Insights

1.  **Overcharging Analysis**:
    
    *   94 orders were overcharged, resulting in an excess of Rs. 11,100.3.
    *   Common discrepancies:
        *   Higher-than-expected weights reported.
        *   Incorrect zone classifications by courier companies.
2.  **Undercharging Analysis**:
    
    *   4 orders were undercharged, causing a loss of Rs. 274.7.
    *   Errors often linked to incorrect weight slabs or zones.
3.  **Correct Billing**:
    
    *   Only 9 orders were billed correctly, highlighting a 90%+ error rate.
4.  **Weight Discrepancies**:
    
    *   Courier-reported weights frequently exceeded ABC-calculated weights.
    *   Suggested the need for stricter reconciliation processes.
5.  **Delivery Zone Mismatches**:
    
    *   15% of orders had zone mismatches, affecting billing accuracy.

* * *

## Business Impact and Recommendations

### Impact of Analysis

1.  **Cost Savings**:
    
    *   Identified overcharges helped recover Rs. 11,100.3.
    *   Improved accuracy in billing to prevent future losses.
2.  **Operational Efficiency**:
    
    *   Insights enabled ABC to renegotiate contracts with courier companies.
    *   Strengthened data integrity and reconciliation processes.
3.  **Customer Trust**:
    
    *   Highlighted commitment to transparency and fairness.

### Recommendations

1.  **Automated Reconciliation**:
    
    *   Implement automated tools to compare internal and courier data in real time.
2.  **Improved Data Sharing**:
    
    *   Enhance collaboration with courier companies to ensure data accuracy.
3.  **Regular Audits**:
    
    *   Conduct routine checks to identify billing discrepancies.
4.  **Advanced Analytics**:
    
    *   Use machine learning models to predict potential discrepancies.
5.  **Process Optimization**:
    
    *   Streamline internal processes for weight calculations and zone mapping.

* * *

## Conclusion

This analysis provided ABC Company with actionable insights to address billing discrepancies with courier companies. By implementing the recommendations, ABC can achieve significant cost savings, improve operational efficiency, and enhance customer trust. The structured approach to data analysis showcased key skills, including Excel formulas, Power BI dashboards, and DAX, underscoring the value of data-driven decision-making in business growth.
