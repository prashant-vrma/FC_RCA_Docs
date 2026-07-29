# Root Cause Analysis (RCA) Framework

## Forecast Adherence RCA Agent

**Version:** 1.0  
**Document Type:** RCA Framework Specification  
**Domain:** Workforce Management (WFM) / Workforce Optimization (WFO)


# 1. Purpose

This document defines the Root Cause Analysis framework used by the Forecast Adherence RCA Agent.

The framework establishes a standardized approach to:

- Detect forecast deviations
- Classify forecast misses
- Identify contributing factors
- Generate evidence-based root causes
- Recommend corrective actions


# 2. RCA Philosophy

Forecast misses should not be treated only as measurement failures.

A forecast deviation is an outcome of multiple possible factors including:

- Demand behavior changes
- Business events
- Operational changes
- Data issues
- Forecast methodology limitations


The RCA framework follows the principle:

"Measure the deviation → Identify the pattern → Determine the driver → Recommend action"


# 3. RCA Measurement Framework


## 3.1 Primary RCA Metric: Forecast Variance %


Formula:

`Forecast Variance % = (Actual Offered - Forecast) / Forecast`


Purpose:

Forecast Variance % is the primary RCA metric because it preserves the direction of error.


Interpretation:


Positive Value:

`Actual Offered > Forecast`

Meaning:

Under Forecast situation.


Negative Value:

`Actual Offered < Forecast`

Meaning:

Over Forecast situation.


Zero:

Perfect forecast.


# 3.2 Reporting Metric: Forecast Adherence %


Formula:

`Forecast Adherence % = 1 - ABS((Actual Offered - Forecast) / Forecast)`


Purpose:

Used for:

- Performance reporting
- Governance
- SLA/SOW measurement


Limitation:

Forecast Adherence removes error direction.


Example:


Scenario A:

Forecast = 10,000

Actual = 12,000

Forecast Variance = +20%

Forecast Adherence = 80%


Scenario B:

Forecast = 10,000

Actual = 8,000

Forecast Variance = -20%

Forecast Adherence = 80%


Both scenarios have identical adherence but require different RCA.


# 4. RCA Investigation Workflow


The RCA process follows these steps:


## Step 1: Detect Forecast Deviation

Identify:

- Significant misses
- Recurring misses
- Abnormal patterns
- High-impact deviations


Detection inputs:

- Forecast Variance %
- Historical performance
- Queue impact
- Business impact


---

## Step 2: Classify Forecast Miss Direction


The system classifies:


## Under Forecast

Condition:

`Forecast Variance % > 0`


Meaning:

Actual demand exceeded expected demand.


Potential investigation areas:

- Missing demand drivers
- Demand increase
- Business events
- Customer behavior changes


---

## Over Forecast

Condition:

`Forecast Variance % < 0`


Meaning:

Forecast demand exceeded actual demand.


Potential investigation areas:

- Demand decline
- Forecast assumption errors
- Volume migration
- Incorrect business assumptions


# 5. RCA Analysis Dimensions


The RCA engine analyzes five major dimensions.


# Dimension 1: Demand Behavior Analysis


Objective:

Determine whether customer demand changed.


Indicators:


Volume Pattern:

- Sudden increase
- Sudden decrease
- Long-term trend change


Analysis:

- Historical comparison
- Year-over-year comparison
- Rolling average comparison


Possible Root Causes:

- Customer behavior change
- Market demand change
- Product demand shift


Recommended Actions:

- Update demand drivers
- Adjust forecasting assumptions
- Increase monitoring


# Dimension 2: Business Event Analysis


Objective:

Identify external business events impacting demand.


Indicators:

- Product launch
- Warranty expiration
- Marketing campaign
- Software release
- Business transition


Possible Root Causes:

- Event not included in forecast
- Incorrect event assumptions
- Event impact underestimated


Recommended Actions:

- Add event-based forecasting inputs
- Improve business collaboration
- Create event impact models


# Dimension 3: Forecast Model Analysis


Objective:

Identify forecasting methodology issues.


Indicators:

- Persistent bias
- Repeated misses
- Poor model performance


Possible Root Causes:

- Missing variables
- Incorrect assumptions
- Model limitations
- Insufficient historical data


Recommended Actions:

- Add new features
- Retrain models
- Evaluate alternative algorithms


# Dimension 4: Data Quality Analysis


Objective:

Determine whether incorrect data influenced forecast performance.


Indicators:

- Missing data
- Incorrect mappings
- Data delays
- Inconsistent definitions


Possible Root Causes:

- Incorrect source data
- Transformation issues
- Data pipeline failures


Recommended Actions:

- Improve validation checks
- Fix data pipelines
- Add monitoring


# Dimension 5: Operational Change Analysis


Objective:

Identify operational changes impacting demand patterns.


Indicators:

- Queue changes
- Routing changes
- Process changes
- Channel migration


Possible Root Causes:

- Routing configuration updates
- Process redesign
- Customer journey changes


Recommended Actions:

- Update forecasting inputs
- Align operational changes with planning


# 6. RCA Classification Taxonomy


Every RCA should be classified into one primary category.


## Category 1: Demand Change

Definition:

Actual customer demand changed from historical expectations.


Examples:

- Volume increase
- Volume decline
- New demand pattern


---

## Category 2: Business Event Impact

Definition:

A planned or unplanned business event affected demand.


Examples:

- Product launch
- Warranty event
- System change


---

## Category 3: Forecast Model Limitation

Definition:

Forecast methodology did not capture actual behavior.


Examples:

- Missing drivers
- Model bias
- Structural shift


---

## Category 4: Data Quality Issue

Definition:

Data problems affected forecast creation or comparison.


Examples:

- Missing values
- Incorrect mapping
- Data delay


---

## Category 5: Operational Change

Definition:

Operational decisions changed demand patterns.


Examples:

- Routing changes
- Queue restructuring
- Process changes


# 7. RCA Evidence Framework


Every root cause must include supporting evidence.


Evidence types:


## Quantitative Evidence

Examples:

- Forecast variance
- Volume change percentage
- Trend comparison
- Historical deviation


## Pattern Evidence

Examples:

- Repeated weekly pattern
- Seasonal behavior
- Queue-specific trend


## Business Evidence

Examples:

- Product event
- Process change
- Operational update


# 8. RCA Confidence Scoring


Each RCA should include confidence.


## High Confidence

Criteria:

- Multiple supporting data points
- Strong correlation
- Business validation available


## Medium Confidence

Criteria:

- Partial evidence
- Some supporting indicators


## Low Confidence

Criteria:

- Limited data
- Multiple possible explanations


# 9. RCA Output Template


The generated RCA should follow this structure:


## Executive Summary

Summary of:

- Forecast issue
- Impact
- Primary reason


## Performance Overview

Include:

- Forecast volume
- Actual volume
- Forecast Variance %
- Forecast Adherence %
- Impact period


## Root Cause

Include:

- Primary category
- Contributing factors
- Supporting evidence


## Business Impact

Include:

- Volume impact
- Operational impact
- Customer impact


## Recommended Actions

Include:

- Immediate action
- Long-term improvement


# 10. RCA Decision Logic


The RCA Agent should follow this reasoning sequence:


1. Identify forecast variance.

↓

2. Determine under forecast or over forecast.

↓

3. Analyze historical patterns.

↓

4. Evaluate business drivers.

↓

5. Identify most probable causes.

↓

6. Generate evidence-based RCA.

↓

7. Recommend corrective actions.


# 11. RCA Quality Standards


A high-quality RCA must be:


## Specific

Avoid:

"Forecast was inaccurate."


Preferred:

"Premium Support demand increased by 18% due to higher warranty expiration volume."


## Evidence-Based

Every conclusion must reference available data.


## Actionable

Recommendations should explain what should change.


## Business-Friendly

Insights should be understandable by non-technical stakeholders.


# 12. Continuous Improvement Framework


The RCA Agent should continuously improve through:


## Feedback Capture

Capture:

- Analyst validation
- RCA corrections
- Recommendation effectiveness


## Knowledge Repository

Store:

- Historical RCA
- Business events
- Corrective actions


## Model Improvement

Use learnings to improve:

- Feature engineering
- Detection logic
- RCA accuracy


# End of Document