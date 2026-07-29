# FC_RCA_Prompt_Library

## Forecast Adherence RCA Agent

**Version:** 1.0  
**Document Type:** Enterprise Prompt Library  
**Project:** Forecast Adherence RCA Agent  
**Owner:** AI Engineering Team / Product Owner


# 1. Purpose

This document serves as the centralized repository for all production prompts used by the Forecast Adherence RCA Agent.

The objectives are to:

- Standardize AI behavior.
- Maintain prompt version control.
- Improve consistency across AI workflows.
- Support prompt evaluation and governance.
- Simplify future prompt enhancements.


# 2. Prompt Management Principles

Every production prompt shall:

- Have a unique Prompt ID.
- Be version controlled.
- Have a documented owner.
- Be reviewed before production deployment.
- Be evaluated using the AI Model Evaluation Framework.
- Follow enterprise AI guardrails.


# 3. Prompt Catalog

| Prompt ID | Prompt Name | Purpose |
|------------|-------------|---------|
| SYS-001 | System Prompt | Defines overall AI behavior |
| PLN-001 | Planning Prompt | Creates execution plans |
| RCA-001 | Root Cause Analysis Prompt | Generates RCA |
| KNO-001 | Knowledge Retrieval Prompt | Retrieves relevant historical knowledge |
| ANA-001 | Analytics Interpretation Prompt | Explains analytical results |
| REC-001 | Recommendation Prompt | Generates corrective actions |
| SUM-001 | Executive Summary Prompt | Produces executive-ready summaries |
| VAL-001 | RCA Validation Prompt | Reviews AI-generated RCA |
| GOV-001 | Governance Review Prompt | Checks compliance with governance rules |
| EVA-001 | Evaluation Prompt | Benchmarks AI responses |


# 4. SYS-001 – System Prompt

## Purpose

Establish the global behavior of the Forecast Adherence RCA Agent.

## Responsibilities

The AI should:

- Act as an enterprise Workforce Management expert.
- Generate explainable Root Cause Analysis.
- Base conclusions on available evidence.
- Never fabricate business facts.
- Clearly distinguish facts from assumptions.
- Use approved knowledge only.
- Recommend practical business actions.
- Maintain a professional and objective tone.


# 5. PLN-001 – Planning Prompt

## Purpose

Plan the analytical workflow before AI reasoning begins.

## Responsibilities

Determine:

- Required datasets.
- Available business context.
- Required calculations.
- Knowledge retrieval requirements.
- Missing information.
- Recommended analysis sequence.


# 6. RCA-001 – Root Cause Analysis Prompt

## Purpose

Generate an end-to-end RCA using analytical evidence and retrieved organizational knowledge.

## Expected Output

The RCA should include:

- Executive Summary
- Business Context
- Forecast Metrics
- Trend Analysis
- Root Cause
- Supporting Evidence
- Confidence Level
- Corrective Recommendations
- Suggested Next Steps


# 7. KNO-001 – Knowledge Retrieval Prompt

## Purpose

Retrieve the most relevant historical RCA cases.

## Retrieval Rules

- Use semantic similarity.
- Retrieve approved knowledge only.
- Rank results by relevance.
- Exclude obsolete knowledge.
- Return supporting references where available.


# 8. ANA-001 – Analytics Interpretation Prompt

## Purpose

Interpret analytical outputs before AI reasoning.

## Analytical Inputs

- Forecast Error
- Forecast Variance
- Forecast Adherence
- Trend Analysis
- Pattern Detection
- Historical Comparisons

## Rules

Forecast Variance determines forecast direction.

Forecast Adherence measures forecast accuracy only.

Do not infer direction from Forecast Adherence.


# 9. REC-001 – Recommendation Prompt

## Purpose

Generate practical recommendations based on the identified root cause.

## Recommendation Rules

Recommendations should:

- Address the identified issue.
- Be actionable.
- Be business relevant.
- Avoid unsupported suggestions.
- Include expected benefits where appropriate.


# 10. SUM-001 – Executive Summary Prompt

## Purpose

Generate a concise executive summary suitable for senior leadership.

The summary should include:

- Business issue
- Key finding
- Business impact
- Primary recommendation
- Confidence level

Avoid excessive technical detail.


# 11. VAL-001 – RCA Validation Prompt

## Purpose

Validate AI-generated RCA before publication.

## Validation Criteria

Verify:

- Root cause accuracy.
- Logical reasoning.
- Evidence support.
- Recommendation quality.
- Business alignment.
- Output completeness.

Flag unsupported conclusions for review.


# 12. GOV-001 – Governance Review Prompt

## Purpose

Ensure AI output complies with governance requirements.

## Governance Checks

- Approved knowledge used.
- No unsupported assumptions.
- Explainable reasoning.
- Appropriate confidence score.
- Required sections completed.
- Audit metadata available.


# 13. EVA-001 – Evaluation Prompt

## Purpose

Benchmark AI responses against approved RCA examples.

## Evaluation Areas

- Business accuracy
- Reasoning quality
- Hallucination detection
- Recommendation relevance
- Explainability
- Consistency


# 14. Prompt Version Control

Each prompt should maintain:

- Prompt ID
- Version
- Owner
- Last Updated Date
- Status (Draft, Review, Approved, Retired)
- Change History


# 15. Prompt Testing

Every prompt revision should be evaluated using:

- Benchmark datasets
- Historical RCA cases
- Edge cases
- Ambiguous scenarios
- Regression tests

Production deployment should occur only after successful validation.


# 16. Prompt Governance

Prompt changes require:

- Technical review.
- Business validation.
- AI evaluation.
- Version update.
- Documentation update.
- Production approval.


# 17. Prompt Lifecycle

Draft

↓

Review

↓

Testing

↓

Business Validation

↓

Approval

↓

Production

↓

Monitoring

↓

Continuous Improvement


# 18. Prompt Maintenance

Regular maintenance activities:

- Review prompt effectiveness.
- Remove redundant instructions.
- Improve clarity.
- Incorporate business feedback.
- Update for new analytical capabilities.
- Archive retired versions.


# 19. Future Prompt Enhancements

Potential future additions:

- Multi-agent collaboration prompts.
- Self-reflection prompts.
- Chain-of-verification prompts.
- Scenario simulation prompts.
- Forecast risk prediction prompts.
- Executive copilot prompts.


# 20. Final Principles

The Prompt Library is the authoritative source for all AI instructions used by the Forecast Adherence RCA Agent.

Well-designed, governed, and version-controlled prompts are essential for producing reliable, explainable, and business-trusted AI outputs.

Every prompt should evolve through structured evaluation, user feedback, and continuous improvement while maintaining consistency across the entire AI platform.


# End of Document