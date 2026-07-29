# RCA Data Requirements and Data Model

## Forecast Adherence RCA Agent

**Version:** 1.0  
**Document Type:** Data Requirements and Data Model Specification  
**Domain:** Workforce Management (WFM) / Workforce Optimization (WFO)


# 1. Purpose

This document defines the data requirements, data structures, business entities, and data relationships required to build the Forecast Adherence RCA Agent.

The objective is to ensure the AI Agent receives complete, accurate, and structured information required to perform reliable Root Cause Analysis.


The document defines:

- Required datasets
- Data attributes
- Data relationships
- Data validation rules
- Data preparation requirements


# 2. Data Architecture Principles


## 2.1 Data Completeness

The RCA Agent requires sufficient historical and current data to identify patterns.

Missing critical data may reduce RCA confidence.


## 2.2 Data Consistency

All datasets must use consistent:


- Queue definitions
- Date formats
- Business segment mapping
- KPI definitions


## 2.3 Historical Context Requirement

Forecast RCA requires comparison against historical behavior.

Recommended historical data availability:


Minimum:

12 months


Preferred:

24+ months


# 3. Required Data Domains


The RCA Agent requires data from the following domains:


# 3.1 Forecast Data


Purpose:

Understand planned demand expectations.


Required attributes:


Forecast_ID

Unique forecast identifier.


Forecast_Date

Date of forecast.


Fiscal_Week

Business week identifier.


Month

Forecast month.


Quarter

Forecast quarter.


Queue_ID

Queue identifier.


Business_Segment

Business category.


Forecast_Volume

Planned contact volume.


Forecast_Type

Manual / Statistical / Final Forecast.


Forecast_Version

Version tracking.


Forecast_Creation_Date

When forecast was generated.


# 3.2 Actual Contact Data


Purpose:

Understand actual operational demand.


Required attributes:


Actual_ID

Unique record identifier.


Actual_Date

Actual contact date.


Fiscal_Week

Business week identifier.


Queue_ID

Queue identifier.


Business_Segment

Business category.


Actual_Offered

Actual contacts offered.


Actual_Handled

Actual contacts handled.


Abandoned_Count

Number of abandoned contacts.


# 3.3 Queue Master Data


Purpose:

Provide queue and business context.


Required attributes:


Queue_ID

Unique queue identifier.


Queue_Name

Queue description.


Business_Segment

Business grouping.


Product_Category

Associated product.


Support_Type

Example:

Basic / Premium / Upsell.


Region

Applicable geography.


Queue_Status

Active / Inactive.


# 3.4 Workforce Data


Purpose:

Understand operational impact.


Required attributes:


Queue_ID

Queue identifier.


Date

Operational date.


Scheduled_HC

Scheduled headcount.


Available_HC

Available headcount.


Shrinkage

Non-productive time.


Occupancy

Operational utilization.


Service_Level

Customer service metric.


# 3.5 Business Event Data


Purpose:

Identify external factors influencing demand.


Required attributes:


Event_ID

Unique event identifier.


Event_Name

Business event name.


Event_Type

Example:

Product launch, system change, promotion.


Start_Date

Event start date.


End_Date

Event end date.


Affected_Queues

Impacted queues.


Business_Impact

Expected impact description.


# 3.6 Historical RCA Data


Purpose:

Enable AI learning through previous analysis.


Required attributes:


RCA_ID

Unique RCA identifier.


Analysis_Date

Date RCA created.


Queue_ID

Impacted queue.


Forecast_Period

Period analyzed.


Forecast_Variance

Calculated variance.


Forecast_Adherence

Calculated adherence.


Variance_Direction

Under Forecast / Over Forecast.


Root_Cause_Category

Root cause classification.


Root_Cause_Description

Detailed explanation.


Evidence

Supporting information.


Recommendation

Corrective action.


Outcome

Post-action result.


# 4. Analytical Data Model


The recommended analytical model consists of:


# Fact Table: Forecast Performance


Purpose:

Store forecast versus actual comparison.


Attributes:


Date

Queue_ID

Forecast_Volume

Actual_Offered

Forecast_Variance

Forecast_Adherence

Variance_Direction


# Fact Table: Workforce Performance


Purpose:

Store operational impact information.


Attributes:


Date

Queue_ID

Scheduled_HC

Available_HC

Service_Level

Occupancy


# Dimension Table: Queue


Attributes:


Queue_ID

Queue_Name

Business_Segment

Product_Category


# Dimension Table: Calendar


Attributes:


Date

Fiscal_Week

Month

Quarter

Year

Holiday_Flag


# Dimension Table: Business Event


Attributes:


Event_ID

Event_Name

Event_Type

Start_Date

End_Date


# 5. Data Relationship Model


The relationships should follow:


Calendar

↓

Forecast Performance

↓

Queue


Calendar

↓

Actual Performance

↓

Queue


Queue

↓

Workforce Performance


Calendar

↓

Business Events


Queue

↓

Historical RCA


# 6. Required Calculated Metrics


The analytics layer should calculate:


# Forecast Variance


Formula:


Forecast Variance % = (Actual Offered - Forecast) / Forecast


Interpretation:


Positive Value:

Actual demand exceeded forecast.

Under Forecast.


Negative Value:

Actual demand was lower than forecast.

Over Forecast.


# Forecast Adherence


Formula:


Forecast Adherence % = 1 - ABS((Actual Offered - Forecast) / Forecast)


Interpretation:


Measures forecast accuracy magnitude.


Important:


Forecast Adherence does not identify Under Forecast or Over Forecast.


# 7. Data Quality Validation Rules


Before RCA generation, validate:


# Forecast Validation


Check:


Forecast value exists.

Forecast period exists.

Queue mapping exists.


# Actual Validation


Check:


Actual Offered exists.

Actual period matches forecast period.


# Mapping Validation


Check:


Queue mapping is consistent.

Business segment mapping exists.


# Historical Validation


Check:


Historical data is available.

Previous RCA records are accessible.


# 8. Data Processing Flow


The recommended processing flow:


Raw Data Sources

↓

Data Ingestion

↓

Data Validation

↓

Data Transformation

↓

Analytical Dataset Creation

↓

RCA Agent Processing


# 9. Data Refresh Requirements


Recommended refresh frequency:


Operational Data:

Daily


Forecast Data:

Based on forecast publication cycle


Historical RCA:

Updated after RCA approval


Business Events:

As events are created or modified


# 10. Data Retention Requirements


Retention should support:


- Historical comparison
- Trend analysis
- Knowledge generation


Recommended:


Operational Data:

24+ months


RCA History:

Long-term retention


Audit Data:

Based on enterprise policy


# 11. Data Security Requirements


The data model must support:


Access Control:

Users only access authorized business data.


Auditability:

Data usage is traceable.


Encryption:

Data remains protected.


# 12. Data Preparation Requirements for AI


Before sending context to the LLM:


The system should provide:


Validated Metrics

↓

Detected Patterns

↓

Relevant Historical Cases

↓

Business Context


The LLM should not receive unnecessary raw data.


# 13. Data Exception Handling


Scenario:


Missing Forecast Data


Action:

Stop RCA generation and request correction.


Scenario:


Missing Historical Data


Action:

Generate RCA with reduced confidence.


Scenario:


Missing Business Context


Action:

Generate analytical RCA and highlight validation requirement.


# 14. Future Data Enhancements


Potential additional data sources:


# Customer Behavior Data


Examples:


- Customer segments
- Contact reasons
- Demand drivers


# Product Lifecycle Data


Examples:


- Product age
- Warranty lifecycle
- Installed base


# External Data


Examples:


- Market events
- Industry trends


# 15. Final Data Architecture Principles


The Forecast Adherence RCA Agent data foundation must remain:


- Complete
- Consistent
- Governed
- Traceable
- Business-aligned


High-quality data enables reliable analytics, and reliable analytics enables trustworthy AI-driven RCA.


# End of Document