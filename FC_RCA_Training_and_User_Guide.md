# FC_RCA_Training_and_User_Guide

## Forecast Adherence RCA Agent

**Version:** 1.0  
**Document Type:** End User Training and User Guide  
**Project:** Forecast Adherence RCA Agent  
**Target Audience:** WFM Analysts, Forecast Analysts, Operations Managers, Business Leaders


# 1. Purpose

This document provides a comprehensive guide for business users to effectively use the Forecast Adherence RCA Agent.

It explains:

- System capabilities
- User roles
- End-to-end workflow
- Best practices
- Frequently Asked Questions (FAQ)
- Troubleshooting guidance


# 2. Intended Users

The application is designed for:

- Forecast Analysts
- Workforce Management Analysts
- Operations Managers
- Business Leaders
- Product Owners
- AI Administrators


# 3. What is the Forecast Adherence RCA Agent?

The Forecast Adherence RCA Agent is an AI-powered analytical platform that automatically investigates forecast misses and generates evidence-based Root Cause Analysis (RCA).

Instead of manually analyzing multiple datasets, the platform:

- Calculates forecasting KPIs
- Detects trends and anomalies
- Retrieves similar historical RCA cases
- Generates explainable AI reasoning
- Recommends corrective actions


# 4. User Roles

## Forecast Analyst

Responsibilities:

- Generate RCA
- Review AI findings
- Validate data
- Submit recommendations


## Operations Manager

Responsibilities:

- Review RCA
- Approve recommendations
- Track corrective actions


## Business Leader

Responsibilities:

- Review executive summaries
- Monitor business trends
- Measure improvement


## AI Administrator

Responsibilities:

- Monitor AI quality
- Review prompts
- Maintain Knowledge Base


# 5. Standard User Workflow

Step 1

Login to the application.


↓

Step 2

Select:

- Business Segment
- Queue
- Analysis Period


↓

Step 3

Verify available data.


↓

Step 4

Click:

Generate RCA


↓

Step 5

Review:

- Executive Summary
- Forecast Metrics
- Root Cause
- Evidence
- Recommendations


↓

Step 6

Approve or request changes.


↓

Step 7

Track implementation actions.


# 6. Understanding Forecast Metrics

## Forecast Error

Difference between Actual Offered and Forecast.

Formula:

Forecast Error = Actual Offered − Forecast


## Forecast Variance

Measures forecast direction.

Formula:

Forecast Variance % = (Actual Offered − Forecast) / Forecast


Interpretation:

Positive Value

Actual exceeded Forecast

Direction:

Under Forecast


Negative Value

Forecast exceeded Actual

Direction:

Over Forecast


## Forecast Adherence

Measures forecast accuracy regardless of direction.

Formula:

Forecast Adherence % = 1 − ABS((Actual Offered − Forecast) / Forecast)


Important:

Forecast Adherence should never be used to determine whether the forecast was over or under.

Always use Forecast Variance for direction.


# 7. Understanding the RCA Screen

Each RCA contains:

## Executive Summary

High-level explanation suitable for leadership.

## Forecast Metrics

Key forecasting calculations.

## Analytical Findings

Observed trends and patterns.

## Root Cause

Primary business reason for the forecast miss.

## Supporting Evidence

Evidence used by the AI.

## Recommendations

Suggested corrective actions.

## Confidence Level

Indicates confidence in the AI's conclusions.


# 8. Reviewing AI Recommendations

Before accepting a recommendation, verify:

- Root cause is logical.
- Evidence supports the conclusion.
- Business context has been considered.
- Recommendation is actionable.
- No unsupported assumptions are present.


# 9. Validating an RCA

Users may choose:

Approve

Approve with Comments

Request Changes

Reject

Reviewer comments should clearly explain any required modifications.


# 10. Viewing Historical RCA

Users can search historical analyses using:

- Queue
- Business Segment
- Date
- Root Cause Category
- Keywords

Historical RCA can be used to identify recurring operational issues.


# 11. Best Practices

Always:

- Verify input data.
- Review supporting evidence.
- Validate recommendations.
- Consider business events.
- Confirm AI conclusions before sharing.

Never:

- Accept unsupported recommendations.
- Ignore confidence levels.
- Publish unreviewed RCA.
- Modify approved knowledge without governance.


# 12. Frequently Asked Questions (FAQ)

## Why does Forecast Adherence not indicate Over Forecast or Under Forecast?

Because the ABS() function removes direction information.

Forecast Variance should always be used to determine direction.


## Why is confidence low?

Possible reasons:

- Missing historical data
- Limited business context
- Unusual demand patterns
- Insufficient evidence


## Can AI replace analyst judgment?

No.

The RCA Agent is a decision-support system.

Final business decisions remain the responsibility of users.


## Why was historical knowledge not used?

Possible reasons:

- No similar approved RCA exists.
- Knowledge has not yet been validated.
- Similarity score was below the retrieval threshold.


# 13. Troubleshooting

Issue:

No RCA generated.

Possible Causes:

- Missing forecast data
- Missing actual data
- AI service unavailable

Recommended Action:

Verify data availability and retry.


Issue:

Incorrect forecast direction.

Recommended Action:

Review Forecast Variance rather than Forecast Adherence.


Issue:

Low confidence.

Recommended Action:

Provide additional business context and review supporting evidence.


# 14. Tips for Better Results

Provide:

- Complete business context
- Accurate forecast data
- Verified actual demand
- Known business events

Review AI findings before approval.


# 15. User Responsibilities

Every user is responsible for:

- Validating AI outputs
- Protecting business data
- Following governance processes
- Reporting incorrect recommendations
- Providing improvement feedback


# 16. Support Model

Business Questions

Contact:

Business Product Owner or WFM SME


Technical Issues

Contact:

Application Support Team


AI Quality Issues

Contact:

AI Product Owner


Access Issues

Contact:

System Administrator


# 17. Training Recommendations

Suggested training sequence:

1. Forecasting Fundamentals
2. Forecast Metrics
3. RCA Methodology
4. Application Navigation
5. AI Validation
6. Governance
7. Hands-on Practice


# 18. Continuous Learning

Users are encouraged to:

- Submit feedback
- Report AI issues
- Suggest improvements
- Participate in knowledge reviews
- Share successful RCA examples


# 19. Key Success Factors

Successful adoption depends on:

- High-quality data
- Business validation
- User engagement
- Continuous learning
- Governance compliance


# 20. Final Guidance

The Forecast Adherence RCA Agent is designed to accelerate analysis, improve consistency, and support better business decisions.

It should be viewed as an intelligent decision-support assistant—not as a replacement for business expertise.

Combining AI-generated insights with analyst judgment and organizational knowledge will produce the highest-quality Root Cause Analysis.


# End of Document