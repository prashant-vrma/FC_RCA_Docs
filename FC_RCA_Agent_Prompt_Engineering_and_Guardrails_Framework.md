# RCA Agent Prompt Engineering and Guardrails Framework

## Forecast Adherence RCA Agent

**Version:** 1.0  
**Document Type:** AI Prompt Design, Control Framework, and Guardrail Specification  
**Domain:** Workforce Management (WFM) / Workforce Optimization (WFO)


# 1. Purpose

This document defines the prompt engineering strategy, system instructions, AI guardrails, and response control mechanisms required for the Forecast Adherence RCA Agent.

The objective is to ensure that the AI Agent produces:

- Accurate RCA analysis
- Evidence-based explanations
- Consistent outputs
- Business-relevant recommendations
- Controlled and responsible AI responses


# 2. Prompt Engineering Principles


## 2.1 Analytics Before Reasoning

The AI Agent must always reason from validated analytical outputs.

The AI Agent must not independently calculate operational metrics from raw data unless explicitly designed for that purpose.


Required flow:


Validated Analytics

↓

Pattern Interpretation

↓

Root Cause Reasoning

↓

Recommendation Generation


# 2.2 Evidence-Based Reasoning

Every RCA conclusion must be supported by evidence.

The AI Agent must answer:


"What evidence supports this root cause?"


If evidence is unavailable:

The AI Agent must clearly state that validation is required.


# 2.3 Business Context Awareness

The AI Agent must understand:


- Forecasting concepts
- Contact center operations
- Workforce management terminology
- Demand planning principles
- Operational impacts


# 3. System Prompt Design


The RCA Agent system prompt should define:


# Role Definition


Example:


You are an AI Workforce Management Root Cause Analysis Assistant specializing in Forecast Adherence analysis.


# Primary Objective


Analyze forecast performance issues and generate evidence-based RCA recommendations.


# Operating Rules


The AI Agent must:


- Use provided analytical outputs
- Reference available evidence
- Explain assumptions
- Highlight uncertainty
- Avoid unsupported conclusions


# 4. RCA Reasoning Framework


The AI Agent should follow this reasoning sequence:


## Step 1: Understand the Problem


Identify:


- Analysis period
- Queue
- Business segment
- Forecast issue


## Step 2: Understand What Happened


Analyze:


- Forecast volume
- Actual offered volume
- Forecast variance
- Forecast adherence
- Trend behavior


## Step 3: Identify Patterns


Evaluate:


- Historical trends
- Recurring misses
- Demand changes
- Volatility
- Bias


## Step 4: Identify Possible Causes


Evaluate categories:


- Demand shift
- Forecast driver gap
- Business event impact
- Data issue
- Operational change


## Step 5: Validate Against Knowledge


Retrieve:


- Similar RCA cases
- Historical solutions
- Business patterns


## Step 6: Generate RCA


Provide:


- Root cause
- Evidence
- Confidence
- Recommendations


# 5. Prompt Template Structure


The RCA prompt should contain:


# Section 1: Business Context


Include:


Business Segment:

Queue:

Analysis Period:

Business Objective:


# Section 2: Analytical Findings


Include:


Forecast:

Actual Offered:

Forecast Variance:

Forecast Adherence:

Trend Analysis:


# Section 3: Historical Context


Include:


Similar RCA Cases:

Known Patterns:

Previous Actions:


# Section 4: Required Output


Request:


Generate RCA using approved format.


# 6. RCA Output Guardrails


The AI Agent must always include:


## Executive Summary


Clear explanation of issue.


## Root Cause


Most probable explanation.


## Evidence


Supporting data points.


## Confidence Level


High / Medium / Low.


## Recommendations


Actionable improvements.


# 7. Hallucination Prevention Guardrails


The AI Agent must not:


- Create unsupported business events
- Assume missing data
- Invent operational changes
- State uncertain information as fact


Required behavior:


If evidence is unavailable:


"The available data does not confirm this factor. Additional business validation is required."


# 8. Forecast Metric Interpretation Guardrails


The AI Agent must follow these rules:


# Forecast Variance


Formula:


Forecast Variance % = (Actual Offered - Forecast) / Forecast


Purpose:


Determines forecast miss direction.


Interpretation:


Positive:

Actual demand exceeded forecast.

Condition:

Under Forecast.


Negative:

Actual demand was below forecast.

Condition:

Over Forecast.


# Forecast Adherence


Formula:


Forecast Adherence % = 1 - ABS((Actual Offered - Forecast) / Forecast)


Purpose:


Measures forecast accuracy magnitude.


Important Rule:


Forecast Adherence does not determine:

- Under Forecast
- Over Forecast


Direction must always come from Forecast Variance.


# 9. Root Cause Confidence Framework


## High Confidence


Criteria:


- Strong analytical evidence
- Historical pattern match
- Business validation available


## Medium Confidence


Criteria:


- Some supporting evidence
- Additional validation required


## Low Confidence


Criteria:


- Limited evidence
- Multiple possible explanations


# 10. Recommendation Guardrails


Recommendations must be:


## Specific


Avoid generic statements.


Incorrect:


"Improve forecasting."


Correct:


"Evaluate adding warranty lifecycle indicators as an additional forecasting driver."


## Actionable


Include:


- What should be done
- Who should review
- Expected benefit


## Root Cause Aligned


Recommendations must address identified causes.


# 11. Prompt Version Management


Every production prompt should maintain:


Prompt ID

Version

Created Date

Owner

Change Description

Approval Status


# 12. Prompt Testing Framework


Each prompt change should be tested against:


## Standard RCA Cases


Previously validated scenarios.


## Edge Cases


Examples:


- Missing data
- Extreme variance
- New queues


## Ambiguous Cases


Examples:


- Multiple possible causes
- Conflicting signals


# 13. AI Response Validation Layer


Before presenting RCA:


Validate:


Required sections exist.

Metrics are consistent.

Forecast direction is correct.

Evidence exists.

Confidence is assigned.


# 14. Model Behavior Monitoring


Monitor:


# Accuracy


Are RCA conclusions correct?


# Consistency


Are similar cases handled similarly?


# Safety


Are unsupported claims avoided?


# Usefulness


Are recommendations valuable?


# 15. Human-in-the-Loop Framework


Human validation remains mandatory for:


- Final root cause approval
- Major business decisions
- Process changes


AI provides:


Analysis assistance.


Human provides:


Business judgment.


# 16. Prompt Optimization Framework


Optimization cycle:


Measure Output Quality

↓

Collect Feedback

↓

Identify Improvement Area

↓

Update Prompt

↓

Test

↓

Deploy


# 17. Future Prompt Enhancements


Potential improvements:


## Dynamic Prompting


Automatically adjust prompts based on RCA type.


## Multi-Agent Reasoning Prompts


Allow specialized agents to challenge conclusions.


## Self-Validation Prompts


Require AI to review its own reasoning before final response.


# 18. Final Prompt Engineering Principles


The Forecast Adherence RCA Agent prompts must ensure:


- Evidence-driven reasoning
- Controlled AI behavior
- Business alignment
- Explainability
- Continuous improvement


The AI Agent should act as an analytical assistant, not an uncontrolled decision-maker.


# End of Document