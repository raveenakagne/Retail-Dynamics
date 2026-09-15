# Retail Dynamics

## Business Requirements Document

## 1. Purpose

The purpose of this document is to translate the Retail Dynamics project objectives into clear, measurable business and analytical requirements.

These requirements will guide the design of the data model, SQL analysis, Python workflows, machine learning components, cloud architecture, and Power BI dashboards.

---

## 2. Business Goals

The platform should help stakeholders:

* Monitor overall retail performance
* Understand customer purchasing behavior
* Identify high-value and repeat customers
* Detect inactive or potentially at-risk customers
* Analyze product and market performance
* Improve customer segmentation
* Discover products commonly purchased together
* Understand customer retention patterns
* Support data-driven sales and marketing decisions

---

## 3. Business Requirements

### BR-001 — Sales Performance Monitoring

The business must be able to monitor revenue, orders, units sold, and average order value over time.

Key dimensions should include:

* Date
* Month
* Quarter
* Year
* Country
* Product
* Customer

---

### BR-002 — Customer Performance Analysis

The business must be able to analyze customer value and purchasing behavior.

The solution should support:

* Total customer spend
* Order frequency
* Average customer order value
* Recency
* Frequency
* Monetary value
* Repeat purchase behavior

---

### BR-003 — Product Performance Analysis

The business must be able to identify:

* Highest-revenue products
* Highest-volume products
* Low-performing products
* Product purchasing trends
* Products frequently purchased together

---

### BR-004 — Geographic Analysis

The business must be able to compare:

* Revenue by country
* Orders by country
* Customers by country
* Average order value by country

---

### BR-005 — Customer Retention Analysis

The solution must support customer-retention analysis including:

* First purchase date
* Repeat purchase behavior
* Customer cohorts
* Retention over time
* Inactive customer identification

---

### BR-006 — Customer Segmentation

The solution should segment customers according to purchasing behavior.

Segmentation may include:

* RFM segmentation
* Behavioral clustering
* High-value customers
* Loyal customers
* New customers
* At-risk or inactive customers

---

### BR-007 — Market Basket Analysis

The business should be able to identify products commonly purchased together.

The analysis should support:

* Frequent itemsets
* Association rules
* Support
* Confidence
* Lift

---

### BR-008 — Predictive Analytics

The platform should investigate whether historical customer behavior can be used to predict future customer outcomes.

Potential predictive targets may include:

* Customer spending category
* Repeat purchase behavior
* Customer segment
* Purchase likelihood

The final target will be selected after exploratory analysis.

---

### BR-009 — Executive Dashboard

Business stakeholders should be able to interact with a Power BI dashboard showing major KPIs and business trends.

The dashboard should include views for:

* Executive performance
* Sales
* Customers
* Products
* Geography
* Retention

---

### BR-010 — Reliable Analytical Data

All KPIs and visualizations must be based on documented, cleaned, and validated data.

The system should identify or handle:

* Missing values
* Duplicate records
* Invalid quantities
* Invalid prices
* Returns and cancellations
* Incorrect data types
* Outliers where relevant

---

## 4. Functional Requirements

### FR-001

The system shall ingest the raw Online Retail II dataset.

### FR-002

The system shall preserve the original raw data without modification.

### FR-003

The system shall generate a cleaned and validated analytical dataset.

### FR-004

The system shall load analytical data into PostgreSQL.

### FR-005

The database shall support dimensional analysis using fact and dimension tables.

### FR-006

SQL queries shall calculate core retail KPIs.

### FR-007

Python workflows shall support exploratory, statistical, and advanced analytics.

### FR-008

The system shall generate customer-level analytical features.

### FR-009

The system shall support machine learning and segmentation workflows.

### FR-010

Power BI shall connect to an analytical data model and display business KPIs.

---

## 5. Non-Functional Requirements

### NFR-001 — Reproducibility

The workflow should be repeatable from raw data to final analytical output.

### NFR-002 — Maintainability

Data-processing logic should be organized into reusable scripts rather than relying exclusively on notebooks.

### NFR-003 — Traceability

Analytical outputs should be traceable back to source data and documented transformations.

### NFR-004 — Security

Credentials and secrets must not be committed to GitHub.

### NFR-005 — Documentation

Important assumptions, transformations, metrics, and analytical decisions must be documented.

### NFR-006 — Data Quality

Core business metrics should only use records meeting documented quality rules.

---

## 6. Initial KPI Definitions

| KPI                  | Initial Definition                                         |
| -------------------- | ---------------------------------------------------------- |
| Revenue              | Sum of valid Quantity × Unit Price                         |
| Orders               | Distinct valid invoice numbers                             |
| Customers            | Distinct valid customer IDs                                |
| Units Sold           | Sum of valid positive quantities                           |
| Average Order Value  | Revenue / Orders                                           |
| Revenue per Customer | Revenue / Customers                                        |
| Purchase Frequency   | Orders / Customers                                         |
| Repeat Customer Rate | Customers with more than one valid order / total customers |
| Recency              | Days since customer’s latest purchase                      |
| Frequency            | Number of customer purchases                               |
| Monetary Value       | Total valid customer spend                                 |

These definitions are provisional and will be validated against the structure and business meaning of the source data.

---

## 7. Data Quality Questions

Before KPI implementation, the analysis must determine:

1. What percentage of records have missing customer IDs?
2. Are duplicate transactions present?
3. How are cancellations represented?
4. How are product returns represented?
5. Are zero or negative prices present?
6. Are zero or negative quantities present?
7. Are product descriptions missing?
8. What is the valid date range?
9. Are there unusual product or invoice codes?
10. Which records should be excluded from revenue calculations?

---

## 8. Acceptance Criteria

This requirements phase will be complete when:

* Major stakeholders are identified
* Key business questions are documented
* Business requirements are defined
* Functional and non-functional requirements are documented
* Initial KPI definitions exist
* Data-quality questions are documented
* Requirements can be mapped to future Agile user stories
