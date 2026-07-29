# RCA AI Agent Test Cases and Evaluation Framework

## Forecast Adherence RCA Agent

**Version:** 1.0  
**Document Type:** AI Testing, Validation, and Evaluation Specification  
**Domain:** Workforce Management (WFM) / Workforce Optimization (WFO)


# 1. Purpose

This document defines the test cases, evaluation methodology, and acceptance criteria for validating the Forecast Adherence RCA Agent.

The objective is to ensure the AI Agent produces:

- Accurate analysis
- Correct metric interpretation
- Evidence-based root causes
- Actionable recommendations
- Consistent business outputs


# 2. Evaluation Philosophy

The RCA Agent should be evaluated on five dimensions:


## Analytical Accuracy

Does the AI correctly interpret forecast performance?


## Reasoning Quality

Does the AI identify logical root causes?


## Evidence Alignment

Are conclusions supported by available data?


## Recommendation Quality

Are recommendations actionable?


## Business Usability

Can business users consume and apply the output?


# 3. Testing Categories


The evaluation framework consists of:


1. Functional Testing

2. Data Interpretation Testing

3. RCA Quality Testing

4. Guardrail Testing

5. Performance Testing

6. User Acceptance Testing


# 4. Functional Test Cases


# Test Case 001: Standard Forecast Miss Analysis


## Scenario

A queue has a forecast miss requiring RCA.


## Input


Forecast:

10,000


Actual Offered:

12,000


Forecast Variance:


(12,000 - 10,000) / 10,000


= +20%


Forecast Adherence:


1 - ABS((12,000 - 10,000) / 10,000)


= 80%


## Expected AI Behavior


The AI should identify:


Direction:

Under Forecast


Reason:

Actual demand exceeded forecast.


The AI should not classify this as Over Forecast.


## Expected Result

Pass if:


- Direction is correct
- Metrics are interpreted correctly
- RCA follows standard format


---

# Test Case 002: Over Forecast Scenario


## Scenario

Actual demand is lower than forecast.


## Input


Forecast:

10,000


Actual Offered:

8,000


Forecast Variance:


(8,000 - 10,000) / 10,000


= -20%


Forecast Adherence:


80%


## Expected AI Behavior


The AI should identify:


Direction:

Over Forecast


Reason:

Forecast exceeded actual demand.


## Expected Result

Pass if:


- AI correctly interprets direction
- Recommendation aligns with over forecasting


---

# Test Case 003: High Forecast Adherence


## Scenario


Forecast is close to actual demand.


## Input


Forecast:

10,000


Actual Offered:

10,500


Forecast Variance:


+5%


Forecast Adherence:


95%


## Expected AI Behavior


AI should identify:


Forecast performance is within acceptable range.


## Expected Result


No unnecessary RCA escalation.


---

# 5. Metric Interpretation Test Cases


# Test Case 004: Forecast Adherence Direction Limitation


## Objective


Ensure AI understands that ABS removes direction.


## Input


Forecast:

10,000


Actual:

12,000


Forecast Adherence:

80%


## Expected Behavior


AI should state:


Forecast Adherence measures accuracy magnitude only.


Direction should be determined using Forecast Variance.


## Expected Result


Pass if AI avoids incorrect directional interpretation.


---

# Test Case 005: Zero Forecast Handling


## Scenario


Forecast value is zero.


## Expected Behavior


AI should not calculate invalid percentage.


Expected response:


Forecast comparison cannot be calculated because forecast baseline is zero.


Additional validation required.


---

# 6. Root Cause Reasoning Test Cases


# Test Case 006: Business Event Impact


## Scenario


Actual demand increased during product launch period.


## Available Evidence


- Forecast miss occurred during launch
- Similar historical launches showed demand increase


## Expected AI Output


Root Cause:


Potential business event impact.


Evidence:


Historical and current demand pattern.


Confidence:


Medium or High depending on evidence availability.


---

# Test Case 007: Forecast Driver Gap


## Scenario


Demand changes due to warranty expiration cycle.


## Expected AI Output


Root Cause:


Forecast model does not include relevant demand driver.


Recommendation:


Evaluate inclusion of warranty lifecycle indicators.


---

# Test Case 008: Insufficient Evidence


## Scenario


Forecast miss exists but no supporting business information exists.


## Expected AI Output


AI should not invent causes.


Expected statement:


Available data is insufficient to confirm the root cause.


Additional validation is required.


---

# 7. Hallucination Test Cases


# Test Case 009: Unsupported Business Event


## Input


No information about system launch, promotion, or business event.


## Expected Behavior


AI should not claim:


"The miss occurred due to a product launch."


## Expected Result


Pass if AI requests validation.


---

# Test Case 010: Missing Historical Data


## Scenario


Only current week data is available.


## Expected Behavior


AI should state:


Historical comparison is unavailable.


Confidence should be reduced.


---

# 8. Recommendation Quality Testing


# Test Case 011: Generic Recommendation Detection


## Incorrect Output


"Improve forecasting accuracy."


## Expected Behavior


AI should provide specific recommendations.


Example:


"Evaluate adding additional demand drivers based on warranty lifecycle changes."


---

# Test Case 012: Root Cause Alignment


## Scenario


Root cause:

Missing business driver.


## Expected Recommendation


Review forecasting inputs and incorporate missing driver.


## Failure Condition


Recommendation unrelated to root cause.


---

# 9. Output Format Validation


The RCA output must contain:


## Required Sections


Executive Summary

Forecast Performance

Variance Analysis

Root Cause

Evidence

Impact

Recommendations

Confidence Level


## Test Result


Pass if all required sections exist.


---

# 10. Confidence Score Evaluation


# High Confidence


Expected when:


- Multiple evidence sources exist
- Historical pattern matches
- Business validation available


# Medium Confidence


Expected when:


- Some evidence exists
- Additional confirmation required


# Low Confidence


Expected when:


- Evidence is limited
- Multiple explanations possible


---

# 11. Knowledge Retrieval Testing


# Test Case 013: Similar RCA Retrieval


## Scenario


Historical RCA exists for similar queue behavior.


## Expected Behavior


AI should reference similar historical patterns.


---

# Test Case 014: Irrelevant Knowledge Filtering


## Scenario


Historical RCA exists but from unrelated business segment.


## Expected Behavior


AI should not use irrelevant knowledge.


---

# 12. Regression Testing Framework


Regression testing should be performed after:


- Prompt changes
- Model changes
- Knowledge Base updates
- Workflow changes


Regression suite should include:


Previously approved RCA cases.

Edge scenarios.

Failure scenarios.


# 13. AI Evaluation Metrics


# RCA Accuracy Rate


Percentage of RCAs accepted by business users.


# Root Cause Precision


Percentage of identified root causes confirmed correct.


# Recommendation Acceptance Rate


Percentage of recommendations considered useful.


# Hallucination Rate


Percentage of unsupported statements generated.


# User Correction Rate


Percentage of outputs requiring significant correction.


# 14. Production Readiness Criteria


The RCA Agent is ready for production when:


Analytics:


- Metric calculations validated
- Forecast direction logic validated


AI:


- RCA quality accepted
- Hallucination controls validated


Business:


- Users approve output quality
- Recommendations are actionable


Governance:


- Monitoring enabled
- Change process established


# 15. Continuous Evaluation Framework


Production monitoring cycle:


Collect RCA Outputs

↓

Measure Quality

↓

Capture User Feedback

↓

Identify Improvement Areas

↓

Improve Prompts / Models / Knowledge

↓

Revalidate


# 16. Final Evaluation Principles


The Forecast Adherence RCA Agent must be evaluated as a business decision-support capability.


Success is achieved when the AI Agent:


- Explains forecast misses accurately
- Uses evidence responsibly
- Provides actionable recommendations
- Builds trust with users


# End of Document