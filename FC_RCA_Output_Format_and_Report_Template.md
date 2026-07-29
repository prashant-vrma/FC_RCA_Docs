# RCA Output Format and Report Template

## Forecast Adherence RCA Agent

**Version:** 1.0  
**Document Type:** RCA Output Structure and Business Reporting Specification  
**Domain:** Workforce Management (WFM) / Workforce Optimization (WFO)


# 1. Purpose

This document defines the standard output structure for the Forecast Adherence RCA Agent.

The objective is to ensure every AI-generated RCA follows a consistent, business-friendly, and evidence-based format.


The RCA output should enable stakeholders to quickly understand:


- What happened
- How significant the issue was
- Why it happened
- What evidence supports the conclusion
- What actions should be taken


# 2. RCA Output Design Principles


## 2.1 Executive-Friendly

The output should be understandable by:


- WFM Analysts
- Workforce Managers
- Operations Leaders
- Business Stakeholders


## 2.2 Evidence-Based

Every root cause must include:


- Supporting data
- Analytical findings
- Business context


## 2.3 Action-Oriented

Every RCA should conclude with:


- Recommended actions
- Ownership
- Expected outcome


# 3. Standard RCA Report Structure


The RCA report should contain the following sections:


1. Executive Summary

2. Forecast Performance Overview

3. Variance Analysis

4. Pattern and Trend Analysis

5. Root Cause Analysis

6. Business Impact Assessment

7. Corrective Actions and Recommendations

8. Confidence Assessment

9. Validation and Feedback


# 4. Executive Summary


## Purpose

Provide a concise overview of the forecast miss.


## Content


Analysis Period:

Queue:

Business Segment:


Forecast Performance:


Forecast Volume:

Actual Offered:

Forecast Variance:

Forecast Adherence:


Variance Direction:


Root Cause Summary:


Recommended Action Summary:


# Example Format


Forecast adherence declined during FY27 Week 05 due to an increase in actual contact demand exceeding forecast expectations. Analysis identified a demand pattern shift associated with increased customer contacts. Additional validation is required to confirm business event impact.


# 5. Forecast Performance Overview


## Purpose

Show the quantitative performance.


Required metrics:


Forecast Volume

Actual Offered

Forecast Variance %

Forecast Adherence %

Variance Direction

Severity Classification


# Metric Definitions


## Forecast Variance


Formula:


Forecast Variance % = (Actual Offered - Forecast) / Forecast


Interpretation:


Positive Variance:

Actual Offered is higher than Forecast.


Classification:

Under Forecast


Negative Variance:

Actual Offered is lower than Forecast.


Classification:

Over Forecast


---


## Forecast Adherence


Formula:


Forecast Adherence % = 1 - ABS((Actual Offered - Forecast) / Forecast)


Interpretation:


Measures how close forecast was to actual demand.


Important:


Forecast Adherence alone cannot identify:

- Under Forecast
- Over Forecast


Direction must be determined using Forecast Variance.


# 6. Variance Analysis


## Purpose

Explain the size and direction of forecast miss.


The analysis should include:


## Magnitude


Example:


Actual demand exceeded forecast by 18%.


## Direction


Example:


The queue experienced Under Forecast conditions.


## Severity


Classification:


Low Impact:

Within ±10%


Medium Impact:

Between ±10% and ±20%


High Impact:

Greater than ±20%


# 7. Pattern and Trend Analysis


## Purpose

Identify behavior patterns contributing to the miss.


The section should analyze:


# Historical Trend


Compare:


- Previous week
- Previous month
- Previous year


# Demand Movement


Identify:


- Growth
- Decline
- Stability


# Volatility


Identify:


- Demand spikes
- Unusual changes
- Recurring fluctuations


# Bias


Identify:


- Consistent Under Forecast
- Consistent Over Forecast


# 8. Root Cause Analysis


## Purpose

Identify the most probable explanation.


Each root cause should contain:


## Root Cause Category


Examples:


Demand Change

Forecast Driver Gap

Business Event Impact

Data Quality Issue

Operational Change


## Root Cause Description


Explain the issue in business terms.


## Supporting Evidence


Include:


- Metric evidence
- Historical comparison
- Business information


## Confidence Level


Classification:


High Confidence:

Strong evidence available.


Medium Confidence:

Some evidence available; validation required.


Low Confidence:

Insufficient evidence available.


# 9. Root Cause Analysis Template


Root Cause:


Category:


Description:


Evidence:


1.

2.

3.


Confidence:


Business Validation Required:


Yes / No


# 10. Business Impact Assessment


## Purpose

Explain operational impact.


The analysis should evaluate:


# Workforce Impact


Examples:


- Staffing imbalance
- Capacity pressure
- Schedule impact


# Customer Impact


Examples:


- Service level risk
- Customer wait time impact


# Financial Impact


Examples:


- Additional staffing requirement
- Efficiency impact


# 11. Corrective Actions and Recommendations


## Purpose

Provide actionable improvements.


Recommendations should be categorized:


# Immediate Actions


Actions to address current impact.


Example:


Review recent demand drivers for impacted queue.


# Short-Term Actions


Actions within current planning cycle.


Example:


Adjust forecast assumptions using updated demand indicators.


# Long-Term Improvements


Process improvement opportunities.


Example:


Introduce additional forecasting drivers.


# 12. Recommendation Format


Action:


Description:


Owner:


Expected Benefit:


Target Timeline:


# 13. Confidence Assessment


The RCA should include:


Overall Confidence:


High / Medium / Low


Reason:


Explain why confidence level was assigned.


# 14. Validation Section


Purpose:

Capture human review.


Reviewer:


Review Date:


Validation Status:


Approved

Approved with Changes

Rejected


Reviewer Comments:


# 15. RCA Visualization Requirements


The report should include visual elements where applicable.


Recommended visuals:


# Forecast vs Actual Trend


Purpose:

Show demand movement.


# Forecast Variance Trend


Purpose:

Show recurring misses.


# Root Cause Contribution View


Purpose:

Show major contributing factors.


# Historical Comparison


Purpose:

Show comparison against previous periods.


# 16. Executive Summary Version


For leadership reporting, generate a shorter version:


Include:


Business Issue

Impact

Root Cause

Recommended Action

Expected Benefit


Exclude:


Detailed technical analysis.


# 17. RCA Quality Checklist


Before publishing, validate:


Metrics are correct.

Forecast direction is accurate.

Evidence is available.

Root cause is logical.

Recommendations are actionable.

Confidence level is assigned.


# 18. RCA Output Governance


Every RCA should store:


RCA ID

Generated Date

User

Data Used

Model Version

Prompt Version

Validation Status


# 19. Future Output Enhancements


Potential enhancements:


## Automated Executive Presentation


Generate leadership-ready slides.


## Conversational RCA Exploration


Allow users to ask follow-up questions.


## Action Tracking


Track implementation of recommendations.


# 20. Final RCA Output Principles


The Forecast Adherence RCA Agent output must remain:


- Structured
- Explainable
- Evidence-driven
- Business-focused
- Action-oriented


A successful RCA is not only an explanation of what happened, but a decision-support tool that enables improvement.


# End of Document