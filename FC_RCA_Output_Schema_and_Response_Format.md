# RCA Output Schema and Response Format

## Forecast Adherence RCA Agent

**Version:** 1.0  
**Document Type:** AI Output Contract Specification  
**Domain:** Workforce Management (WFM) / Workforce Optimization (WFO)


# 1. Purpose

This document defines the standardized output structure expected from the Forecast Adherence RCA Agent.

The objective is to ensure every AI-generated Root Cause Analysis (RCA) is:

- Consistent
- Explainable
- Evidence-based
- Business-friendly
- Actionable
- Traceable to analytical findings


# 2. Output Design Principles


## 2.1 Fact Before Explanation

The RCA must first present factual analysis before generating explanations.

The output sequence should always be:

1. Forecast performance facts
2. Variance identification
3. Pattern analysis
4. Root cause evaluation
5. Recommendations


The AI must not start with assumptions or business explanations without analytical evidence.


# 2.2 Preserve Forecast Direction


Forecast Adherence alone cannot identify whether the business was under forecast or over forecast because ABS removes the direction.


Therefore, Forecast Variance must always be included.


## Forecast Variance Direction


Formula:

Forecast Variance % = (Actual Offered - Forecast) / Forecast


Interpretation:


Positive Forecast Variance:

Actual Offered was higher than Forecast.

Business interpretation:

Under Forecast condition.


Negative Forecast Variance:

Actual Offered was lower than Forecast.

Business interpretation:

Over Forecast condition.


# 2.3 Separate Accuracy from Direction


Forecast Adherence measures closeness between forecast and actuals.


Formula:

Forecast Adherence % = 1 - ABS((Actual Offered - Forecast) / Forecast)


Usage:

Forecast Adherence = Accuracy measurement


Forecast Variance = Direction and magnitude measurement


Both metrics must be presented together.


# 3. RCA Output Structure


The final RCA response must contain the following sections:


1. RCA Header

2. Executive Summary

3. Forecast Performance Summary

4. Variance Analysis

5. Root Cause Analysis

6. Supporting Evidence

7. Business Impact

8. Confidence Assessment

9. Recommended Actions

10. Follow-Up Requirements


# 4. RCA Header


The RCA header must include:


RCA ID

Analysis Period

Queue

Business Segment

Generated Date

RCA Version


Example:

RCA ID: RCA_2026_07_001

Analysis Period: FY27 Week 05

Queue: Premium Support

Business Segment: Upsell

Generated Date: 2026-07-28

RCA Version: 1.0


# 5. Executive Summary


## Purpose

Provide an executive-level summary of the forecast miss.


The summary must answer:


What happened?

Why did it happen?

What was the impact?


Example:


During FY27 Week 05, Premium Support demand exceeded forecast expectations by 18%.

The primary contributing factor identified was increased customer demand associated with warranty expiration activity.

The forecast miss created additional workforce planning pressure and potential service level risk.


# 6. Forecast Performance Summary


The RCA must include the following metrics:


Forecast Volume

Definition:

Planned contact demand.


Actual Offered

Definition:

Actual contacts received.


Forecast Variance %

Definition:

Directional difference between actual demand and forecast.


Forecast Adherence %

Definition:

Overall forecast accuracy measurement.


# 7. Variance Analysis


## Purpose

Explain the magnitude and direction of the forecast miss.


The analysis must include:


- Under Forecast or Over Forecast classification
- Variance percentage
- Duration of issue
- Whether issue is isolated or recurring


Example:


Actual Offered volume was 18% higher than forecast during FY27 Week 05.

This represents an Under Forecast condition.

The same pattern was observed for three consecutive weeks, indicating a potential demand pattern change.


# 8. Root Cause Analysis Framework


The RCA Agent must evaluate the following root cause categories.


# 8.1 Demand Change


Definition:

Customer demand changed from historical expectations.


Possible causes:

- Increase in customer contacts
- Decrease in customer contacts
- New demand behavior
- Customer segment changes


Required evidence:

- Volume trend
- Historical comparison
- Demand pattern analysis


# 8.2 Business Event Impact


Definition:

A known business activity influenced demand.


Possible causes:

- Product launch
- Warranty change
- Marketing campaign
- System release
- Business program change


Required evidence:

- Event timing
- Business confirmation
- Volume relationship


# 8.3 Forecast Model Limitation


Definition:

The forecasting approach did not capture current demand behavior.


Possible causes:

- Missing forecast drivers
- Structural demand shift
- Historical pattern no longer valid
- Model limitations


Required evidence:

- Forecast bias trend
- Historical accuracy trend
- Missing variables


# 8.4 Data Quality Issue


Definition:

Incorrect or incomplete data affected forecast analysis.


Possible causes:

- Missing records
- Incorrect queue mapping
- Data delay
- Data inconsistency


Required evidence:

- Data validation results
- Source comparison


# 8.5 Operational Change


Definition:

Operational changes influenced demand.


Possible causes:

- Queue restructuring
- Routing changes
- Process changes
- Customer journey changes


Required evidence:

- Operational change records
- Timeline correlation


# 9. Supporting Evidence


Every RCA conclusion must include supporting evidence.


Evidence may include:


- Forecast variance
- Historical trends
- Demand movement
- Business events
- Operational changes
- Statistical patterns


Example:


Evidence:

1. Actual Offered volume increased by 22% compared with the previous four-week average.

2. Warranty expiration population increased during the same period.

3. Similar demand behavior was observed during previous warranty cycles.


# 10. Business Impact Assessment


The RCA must translate forecast misses into business impact.


## Workforce Impact


Evaluate:

- Additional staffing requirement
- Capacity pressure
- Overtime risk
- Schedule impact


## Customer Impact


Evaluate:

- Service level risk
- Customer wait time impact
- Customer experience impact


## Financial Impact


Evaluate:

- Additional operational cost
- Productivity impact
- Efficiency impact


# 11. Confidence Assessment


The RCA Agent must assign confidence based on available evidence.


# High Confidence


Criteria:

- Multiple supporting data points
- Strong analytical relationship
- Business validation available


# Medium Confidence


Criteria:

- Some supporting evidence available
- Additional validation required


# Low Confidence


Criteria:

- Limited evidence
- Multiple possible causes
- Insufficient information


If confidence is Low, the RCA must clearly state:

"Insufficient evidence available to determine the exact root cause."


# 12. Recommended Actions


Recommendations must be actionable and evidence-based.


The RCA should provide:


## Immediate Actions


Examples:

- Validate demand drivers
- Review business events
- Adjust operational planning


## Long-Term Improvements


Examples:

- Add new forecast drivers
- Improve forecasting methodology
- Enhance monitoring
- Improve business event integration


# 13. Follow-Up Requirements


Every recommendation should include:


Owner

Action

Due Date

Validation Method


Example:


Owner:

Forecasting Team


Action:

Evaluate warranty expiration data as a forecast driver.


Due Date:

Next forecast cycle


Validation Method:

Measure improvement in forecast accuracy.


# 14. Machine-Readable RCA Schema


The system output should internally maintain the following structure:


rca_id

analysis_period

queue

business_segment

forecast_volume

actual_offered

forecast_variance_percent

forecast_adherence_percent

variance_direction

root_cause_category

root_cause_description

supporting_evidence

business_impact

confidence_level

recommendations


# 15. Output Validation Rules


Before presenting the final RCA, validate:


## Mandatory Information


The RCA must contain:


- Forecast volume
- Actual Offered volume
- Forecast Variance %
- Forecast Adherence %
- Variance direction
- Root cause category
- Supporting evidence
- Recommendations


## AI Quality Rules


The RCA must not:


- Create unsupported business explanations
- Ignore forecast direction
- Use only Forecast Adherence for interpretation
- Provide generic recommendations
- Hide uncertainty


# 16. Final RCA Quality Standard


A high-quality RCA must answer:


What happened?

How large was the forecast miss?

Was it Under Forecast or Over Forecast?

Why did it happen?

What evidence supports the conclusion?

What actions should be taken?


# End of Document