# RCA Analytics Framework and Logic

## Forecast Adherence RCA Agent

**Version:** 1.0  
**Document Type:** Analytical Framework Specification  
**Domain:** Workforce Management (WFM) / Workforce Optimization (WFO)


# 1. Purpose

This document defines the analytical framework, calculation logic, diagnostic approach, and decision rules used by the Forecast Adherence RCA Agent.

The objective is to ensure the RCA engine performs structured analysis before generating AI-driven explanations.


The analytics framework enables the system to identify:

- Forecast misses
- Miss direction
- Demand patterns
- Forecast bias
- Volatility
- Potential root causes
- Business impact


# 2. Analytical Principles


## 2.1 Separate Measurement from Explanation


The analytics layer determines:

- What happened
- How large the deviation was
- Whether the deviation was recurring


The AI reasoning layer determines:

- Why it happened
- What actions should be considered


# 2.2 Preserve Forecast Miss Direction


Forecast accuracy metrics alone are insufficient.

The system must always retain:


Forecast Variance:

Direction of forecast miss.


Forecast Adherence:

Magnitude of forecast accuracy.


Both metrics must be evaluated together.


# 3. Core Forecast Metrics


# 3.1 Forecast Variance


Definition:

Measures the directional difference between actual demand and forecast demand.


Formula:


Forecast Variance % = (Actual Offered - Forecast) / Forecast


Interpretation:


Positive Variance:

Actual Offered is greater than Forecast.


Business Meaning:

Under Forecast.


Example:


Forecast:

10,000 contacts


Actual Offered:

12,000 contacts


Forecast Variance:

+20%


Interpretation:

Demand was higher than expected.


---


Negative Variance:

Actual Offered is lower than Forecast.


Business Meaning:

Over Forecast.


Example:


Forecast:

10,000 contacts


Actual Offered:

8,000 contacts


Forecast Variance:

-20%


Interpretation:

Demand was lower than expected.


# 3.2 Forecast Adherence


Definition:

Measures forecast accuracy regardless of direction.


Formula:


Forecast Adherence % = 1 - ABS((Actual Offered - Forecast) / Forecast)


Purpose:

Used to measure how close forecast was to actual demand.


Important Rule:


Forecast Adherence cannot determine:

- Under Forecast
- Over Forecast


Direction must come from Forecast Variance.


# 4. Forecast Miss Classification Logic


The RCA Agent should classify forecast performance using:


# Under Forecast


Condition:


Actual Offered > Forecast


AND


Forecast Variance % is positive


Meaning:


Demand exceeded expectations.


Potential investigation areas:


- Demand increase
- Missing drivers
- Business events
- Forecast model limitation


# Over Forecast


Condition:


Actual Offered < Forecast


AND


Forecast Variance % is negative


Meaning:


Forecast exceeded actual demand.


Potential investigation areas:


- Demand decline
- Incorrect assumptions
- Business changes
- Forecast model limitation


# 5. Severity Classification


The system should classify forecast misses based on magnitude.


Recommended thresholds:


Low Impact:

Forecast Variance within ±10%


Medium Impact:

Forecast Variance between ±10% and ±20%


High Impact:

Forecast Variance greater than ±20%


Note:

Thresholds should be configurable based on business requirements.


# 6. Trend Analysis Framework


## Purpose

Identify whether forecast misses are isolated or recurring.


The system should evaluate:


# Short-Term Trend


Analysis period:

Recent weeks.


Purpose:

Identify immediate changes.


Metrics:

- Week-over-week variance
- Recent demand movement


# Long-Term Trend


Analysis period:

Historical months or quarters.


Purpose:

Identify structural changes.


Metrics:

- Monthly trend
- Seasonal pattern
- Historical bias


# 7. Bias Analysis


## Purpose

Identify systematic forecast error.


# Under Forecast Bias


Definition:

Actual demand consistently exceeds forecast.


Indicators:


- Positive average Forecast Variance
- Multiple consecutive Under Forecast periods


Potential causes:


- Missing demand driver
- Growth not captured
- Forecast assumption issue


# Over Forecast Bias


Definition:

Forecast consistently exceeds actual demand.


Indicators:


- Negative average Forecast Variance
- Multiple consecutive Over Forecast periods


Potential causes:


- Demand decline
- Outdated assumptions
- Incorrect forecast inputs


# 8. Volatility Analysis


## Purpose

Identify unstable demand behavior.


The system should evaluate:


# Demand Volatility


Metrics:


- Standard deviation
- Coefficient of variation
- Week-over-week movement


# High Volatility Indicators


Examples:


- Sudden demand spikes
- Large weekly swings
- Unpredictable behavior


Potential causes:


- Business events
- Customer behavior changes
- External factors


# 9. Historical Comparison Analysis


The RCA engine should compare:


## Previous Week


Purpose:

Identify recent changes.


## Previous Month


Purpose:

Identify medium-term trends.


## Previous Year


Purpose:

Identify seasonal differences.


Comparison areas:


- Volume
- Forecast accuracy
- Variance direction
- Demand behavior


# 10. Queue-Level Analysis


The analysis should be performed at:


Queue Level:

Identify specific operational impact.


Business Segment Level:

Identify broader patterns.


Portfolio Level:

Identify enterprise trends.


The system should avoid generalizing portfolio-level findings to individual queues without evidence.


# 11. Root Cause Analytical Categories


The analytics engine should evaluate the following categories:


# Demand Change


Signals:


- Actual volume movement
- Customer behavior change
- Trend shift


# Forecast Driver Gap


Signals:


- Missing correlation between drivers and demand
- Historical model limitations


# Business Event Impact


Signals:


- Event timing matches demand movement
- Known business activity


# Data Quality Issue


Signals:


- Missing records
- Incorrect mappings
- Data inconsistencies


# Operational Change


Signals:


- Queue changes
- Routing changes
- Process changes


# 12. RCA Evidence Scoring


Each potential root cause should receive an evidence score.


Evaluation factors:


Data Evidence:

Is there measurable support?


Historical Similarity:

Has this occurred before?


Business Confirmation:

Is there supporting business information?


Pattern Strength:

Is the relationship consistent?


# 13. Confidence Calculation Logic


Recommended confidence levels:


# High Confidence


Criteria:

- Multiple supporting signals
- Clear pattern
- Business validation available


# Medium Confidence


Criteria:

- Some supporting signals
- Additional validation required


# Low Confidence


Criteria:

- Limited evidence
- Multiple possible explanations


# 14. Analytical Decision Flow


Step 1:

Calculate Forecast Variance.


Step 2:

Determine Under Forecast or Over Forecast.


Step 3:

Measure severity.


Step 4:

Analyze trends.


Step 5:

Evaluate bias.


Step 6:

Identify patterns.


Step 7:

Compare historical RCA cases.


Step 8:

Generate root cause hypotheses.


Step 9:

Assign confidence.


Step 10:

Pass findings to AI reasoning layer.


# 15. Analytics Output Contract


The analytics engine should provide:


Forecast Volume

Actual Offered

Forecast Variance %

Forecast Adherence %

Variance Direction

Severity Classification

Trend Findings

Bias Findings

Volatility Findings

Historical Comparison

Potential Root Causes

Evidence Supporting Each Cause


# 16. Quality Rules


The analytics engine must:


- Calculate metrics consistently
- Preserve forecast direction
- Avoid unsupported conclusions
- Maintain traceability
- Provide evidence for every finding


# 17. Final Analytical Framework Principles


The Forecast Adherence RCA Agent analytics layer must remain:


- Accurate
- Transparent
- Explainable
- Evidence-driven
- Business-aligned


Analytics identifies the pattern.

AI explains the story.

Human expertise validates the final RCA.


# End of Document