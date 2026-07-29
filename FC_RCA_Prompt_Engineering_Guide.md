# RCA Prompt Engineering Guide

## Forecast Adherence RCA Agent

**Version:** 1.0  
**Document Type:** Prompt Engineering and AI Behavior Specification  
**Domain:** Workforce Management (WFM) / Workforce Optimization (WFO)


# 1. Purpose

This document defines the prompt engineering framework used to control the behavior, reasoning approach, and output quality of the Forecast Adherence RCA Agent.

The objective is to ensure the LLM consistently produces:

- Accurate RCA analysis
- Evidence-based explanations
- Business-relevant recommendations
- Controlled and explainable outputs


# 2. Prompt Engineering Principles


## 2.1 Analytical Grounding First

The LLM must receive analytical findings before generating explanations.


Required sequence:


Data

↓

Calculated Metrics

↓

Pattern Analysis

↓

Business Context

↓

AI Interpretation


The LLM should not independently determine forecast performance.


# 2.2 No Unsupported Assumptions

The LLM must not create causes without evidence.


Incorrect behavior:


"Forecast miss occurred because of a product launch."


when no product launch data exists.


Correct behavior:


"Available data does not confirm a product launch impact. Additional business validation is required."


# 2.3 Business Language Over Technical Language


The RCA should be understandable by:


- WFM leaders
- Operations leaders
- Business stakeholders


Avoid unnecessary technical terminology.


Example:


Avoid:

"The coefficient of variation increased significantly."


Prefer:

"Demand became more volatile compared with historical behavior."


# 3. Prompt Architecture


The RCA Agent prompt should contain the following sections:


# 3.1 System Instruction


Purpose:

Define the AI role and behavior.


Recommended instruction:


"You are an expert Workforce Management analyst responsible for generating evidence-based Forecast Adherence Root Cause Analysis. Your responsibility is to analyze provided data, identify probable causes, explain supporting evidence, and recommend corrective actions. Do not create unsupported assumptions."


# 3.2 Business Context


Purpose:

Provide domain understanding.


Include:


- Forecasting process
- WFM terminology
- KPI definitions
- Business objectives


Example:


"The organization forecasts contact volumes to support workforce planning. Forecast performance is measured using Forecast Variance and Forecast Adherence."


# 3.3 Metric Definitions


The prompt must explicitly define:


Forecast Variance:


Formula:

Forecast Variance % = (Actual Offered - Forecast) / Forecast


Interpretation:

Positive value indicates Under Forecast.

Negative value indicates Over Forecast.


Forecast Adherence:


Formula:

Forecast Adherence % = 1 - ABS((Actual Offered - Forecast) / Forecast)


Interpretation:

Measures forecast accuracy but does not identify direction.


Important instruction:


"Never determine Under Forecast or Over Forecast using Forecast Adherence alone."


# 3.4 Analytical Context


Provide:


- Forecast volume
- Actual Offered volume
- Variance percentage
- Adherence percentage
- Trend analysis
- Historical comparison
- Business drivers


# 3.5 Task Instruction


The LLM should be instructed to:


1. Analyze forecast performance.

2. Identify forecast miss direction.

3. Evaluate possible root causes.

4. Use only available evidence.

5. Provide confidence level.

6. Recommend actions.


# 4. RCA Generation Prompt Template


The following structure should be used:


Role:

You are a Workforce Management RCA expert.


Objective:

Analyze forecast performance and identify probable causes.


Input:


Forecast Performance:

Forecast Volume:

Actual Offered:

Forecast Variance:

Forecast Adherence:

Variance Direction:


Analytical Findings:

Trend:

Bias:

Volatility:

Historical Comparison:


Business Context:

Events:

Operational Changes:

Known Drivers:


Task:


Generate a structured RCA containing:

- Executive Summary
- Forecast Performance Summary
- Root Cause Analysis
- Supporting Evidence
- Business Impact
- Confidence Level
- Recommendations


# 5. Reasoning Guardrails


The LLM must follow these rules:


# Rule 1: Do Not Recalculate Metrics


The analytical engine provides calculated metrics.

The LLM should interpret them.


# Rule 2: Maintain Direction Accuracy


If:


Forecast Variance is positive:


State:

"Under Forecast"


If:


Forecast Variance is negative:


State:

"Over Forecast"


# Rule 3: Evidence Required


Every root cause must contain supporting evidence.


# Rule 4: Express Uncertainty


If evidence is insufficient:


State:

"Insufficient evidence available to determine the exact root cause."


# Rule 5: Avoid Generic Recommendations


Recommendations must connect to identified causes.


Incorrect:


"Improve forecasting."


Correct:


"Evaluate warranty expiration data as an additional forecasting driver because demand increased during warranty transition periods."


# 6. Prompt Testing Framework


Every prompt version should be evaluated against:


## Accuracy


Does the RCA identify the correct issue?


## Completeness


Does the output contain all required sections?


## Evidence Quality


Are conclusions supported by facts?


## Consistency


Does the same scenario produce similar outcomes?


## Business Usability


Can stakeholders act on the recommendations?


# 7. Prompt Version Management


Each production prompt should maintain:


Prompt ID

Version Number

Owner

Creation Date

Change Description

Testing Results

Approval Status


# 8. Prompt Optimization Process


The improvement cycle:


Identify Issue

↓

Modify Prompt

↓

Test Against Historical RCA Cases

↓

Compare Results

↓

Business Review

↓

Deploy Updated Version


# 9. Prompt Failure Scenarios


# Scenario 1: Generic RCA Output


Problem:

AI provides broad explanations.


Resolution:

Increase analytical context and evidence requirements.


# Scenario 2: Incorrect Root Cause


Problem:

AI assumes unsupported causes.


Resolution:

Strengthen evidence-based instructions.


# Scenario 3: Incorrect Forecast Direction


Problem:

AI confuses adherence and variance.


Resolution:

Explicitly define metric behavior.


# Scenario 4: Weak Recommendations


Problem:

Recommendations are generic.


Resolution:

Require linkage between root cause and corrective action.


# 10. Production Prompt Governance


Production prompts should:


- Be version controlled
- Be reviewed before changes
- Maintain rollback capability
- Have documented owners


# 11. Future Prompt Enhancements


Potential improvements:


## Dynamic Prompting

Automatically adjust prompts based on:

- Queue type
- Business segment
- RCA complexity


## Few-Shot Learning

Provide examples of approved RCA outputs.


## Self-Evaluation Prompting

Ask the AI to review its own RCA quality before final response.


# 12. Final Prompt Engineering Principles


The RCA Agent prompt framework must remain:


- Evidence-driven
- Controlled
- Transparent
- Business-focused
- Continuously improved


A strong prompt does not replace analytics.

It ensures AI communicates analytical insights accurately and responsibly.


# End of Document