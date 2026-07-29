# RCA_Data_Dictionary_and_Business_Rules

## Forecast Adherence RCA Agent

**Version:** 1.0  
**Document Type:** Enterprise Data Dictionary and Business Rules Specification  
**Domain:** Workforce Management (WFM) / Workforce Optimization (WFO)


# 1. Purpose

This document defines the enterprise data dictionary, field definitions, data quality standards, transformation rules, validation logic, and business rules for the Forecast Adherence RCA Agent.

The objective is to establish a single source of truth for all data elements used throughout the solution.

This document should be referenced by:

- Business Analysts
- WFM Analysts
- Data Engineers
- AI Engineers
- Solution Architects
- Application Developers
- QA Engineers


# 2. Data Domains

The solution uses the following logical data domains:

- Forecast Data
- Actual Volume Data
- Queue Master Data
- Calendar Data
- Business Event Data
- Forecast Driver Data
- Historical RCA Data
- Knowledge Base Data
- User Data
- System Metadata


# 3. Forecast Data Dictionary


## Forecast

Description:

Forecasted contact volume for a selected time period.

Data Type:

Decimal

Required:

Yes

Business Rule:

Must be greater than or equal to zero.


## Forecast Date

Description:

Date associated with the forecast.

Data Type:

Date

Required:

Yes


## Forecast Week

Description:

Business forecasting week.

Data Type:

String


## Forecast Month

Description:

Business forecasting month.

Data Type:

String


## Forecast Quarter

Description:

Business forecasting quarter.

Data Type:

String


## Forecast Version

Description:

Version of the approved forecast.

Data Type:

String


# 4. Actual Volume Data Dictionary


## Actual Offered

Description:

Actual customer contacts received.

Data Type:

Decimal

Required:

Yes

Business Rule:

Cannot be negative.


## Actual Handled

Description:

Contacts handled by operations.

Data Type:

Decimal


## Actual Abandoned

Description:

Customer contacts abandoned before handling.

Data Type:

Decimal


# 5. Queue Master Data


## Queue ID

Description:

Unique queue identifier.

Data Type:

String


## Queue Name

Description:

Business-friendly queue name.

Data Type:

String


## Business Segment

Description:

Operational business area.

Examples:

- Basic
- Premium
- Enterprise


## Region

Description:

Geographical business region.


## Language

Description:

Primary customer language.


# 6. Calendar Data


## Calendar Date

Description:

Business calendar date.


## Fiscal Week

Description:

Organization fiscal week.


## Fiscal Month

Description:

Organization fiscal month.


## Fiscal Quarter

Description:

Organization fiscal quarter.


## Holiday Indicator

Description:

Indicates whether the date is a business holiday.


Allowed Values:

Yes

No


## Weekend Indicator

Allowed Values:

Yes

No


# 7. Forecast Driver Data


## Product Launch Indicator

Description:

Identifies active product launches.


## Warranty Expiration Indicator

Description:

Identifies warranty lifecycle changes.


## Marketing Campaign Indicator

Description:

Indicates campaign activity.


## System Outage Indicator

Description:

Identifies operational disruption.


## Business Event Description

Description:

Narrative describing the business event.


# 8. Historical RCA Data


## RCA ID

Unique identifier.


## Root Cause Category

Examples:

- Demand Shift
- Forecast Driver Gap
- Business Event
- Data Quality
- Operational Issue
- Process Change


## Root Cause Description

Business explanation for the forecast miss.


## Recommendation

Corrective action recommended.


## Validation Status

Allowed Values:

- Draft
- Under Review
- Approved
- Rejected


# 9. AI Metadata


## Confidence Score

Description:

Confidence assigned to AI output.

Allowed Values:

High

Medium

Low


## Prompt Version

Description:

Prompt version used during generation.


## Model Version

Description:

LLM version used.


## Knowledge Version

Description:

Knowledge Base version.


# 10. Business Rule Definitions


## Rule 1

Forecast must be greater than or equal to zero.


## Rule 2

Actual Offered must be greater than or equal to zero.


## Rule 3

Forecast Variance determines forecast direction.


Formula:

Forecast Variance % = (Actual Offered - Forecast) / Forecast


Interpretation:

Positive Value

Under Forecast


Negative Value

Over Forecast


## Rule 4

Forecast Adherence measures only forecast accuracy magnitude.


Formula:

Forecast Adherence % = 1 - ABS((Actual Offered - Forecast) / Forecast)


Important:

ABS removes forecast direction.

Direction must always be determined using Forecast Variance.


## Rule 5

Forecast value equal to zero requires special handling.

Forecast percentage calculations must not divide by zero.


## Rule 6

Every RCA must reference supporting evidence.


## Rule 7

Every AI recommendation must align with the identified root cause.


## Rule 8

Only approved knowledge may be used during production RCA generation.


# 11. Data Validation Rules


Validate:


Forecast is available.


Actual Offered is available.


Queue exists.


Business Segment exists.


Analysis Period is valid.


Historical data available where required.


# 12. Data Quality Rules


Required quality dimensions:


Completeness

Accuracy

Consistency

Validity

Timeliness

Uniqueness


# 13. Data Transformation Rules


Transformations include:


Standardize queue names.


Normalize business segment values.


Convert dates to fiscal calendar.


Create derived forecasting metrics.


Generate analytical features.


# 14. Derived Metrics


Forecast Error

= Actual Offered - Forecast


Forecast Variance %

= (Actual Offered - Forecast) / Forecast


Forecast Adherence %

= 1 - ABS((Actual Offered - Forecast) / Forecast)


Absolute Forecast Error

= ABS(Actual Offered - Forecast)


Forecast Bias

Calculated across multiple periods using Forecast Error trends.


# 15. Missing Data Rules


If Forecast is missing:

Stop RCA generation.


If Actual Offered is missing:

Stop RCA generation.


If Business Context is missing:

Continue analysis but reduce confidence.


If Historical RCA is unavailable:

Continue using analytical evidence only.


# 16. Data Ownership


Forecast Data

Owner:

WFM Forecasting Team


Actual Data

Owner:

Operations Reporting Team


Business Events

Owner:

Business Operations


Knowledge Base

Owner:

Business SMEs


AI Metadata

Owner:

AI Platform Team


# 17. Data Governance


The data model shall support:

- Data lineage
- Auditability
- Version control
- Metadata management
- Role-based access
- Retention policies


# 18. Future Data Enhancements


Potential additions:

- External demand indicators
- Weather impact
- Economic indicators
- Customer sentiment
- Marketing calendars
- Product lifecycle intelligence


# 19. Reference Standards


All calculations should use approved enterprise definitions.

Business rules shall override AI assumptions.

Analytical calculations shall be validated before AI reasoning begins.


# 20. Final Principles


The Forecast Adherence RCA Agent relies on consistent, governed, and high-quality data.

This document serves as the authoritative reference for every data element, transformation, and business rule used throughout the solution lifecycle.


# End of Document