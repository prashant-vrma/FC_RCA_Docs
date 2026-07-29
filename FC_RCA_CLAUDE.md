# CLAUDE.md

# Forecast Adherence RCA Agent
## Master Repository Guide for Humans and AI Coding Assistants

**Project:** Forecast Adherence RCA Agent  
**Version:** 1.0  
**Document Type:** Master Repository Guide  
**Audience:** Developers, Architects, AI Coding Assistants (Claude, Cursor, GitHub Copilot, Windsurf, DataRobot AI, etc.)

---

# 1. Purpose

Welcome to the Forecast Adherence RCA Agent repository.

This repository contains the complete enterprise documentation required to design, build, test, deploy, and operate an AI-powered Root Cause Analysis (RCA) platform for Forecast Adherence in Workforce Management (WFM).

This file is the primary entry point for every developer and AI coding assistant working on this project.

Read this document before making any code or documentation changes.

---

# 2. Project Vision

The Forecast Adherence RCA Agent is an enterprise AI application that automatically analyzes forecast misses, identifies probable root causes, retrieves historical organizational knowledge, and generates explainable, evidence-based recommendations.

The platform combines:

- Workforce Management analytics
- AI reasoning
- Retrieval-Augmented Generation (RAG)
- Multi-agent orchestration
- Business rules
- Statistical analysis
- Executive reporting

The objective is to reduce manual RCA effort while improving consistency, transparency, and business decision-making.

---

# 3. Core Business Problem

Business users spend significant time manually investigating forecast adherence misses.

The AI platform automates this process by:

- Validating input data
- Calculating forecasting metrics
- Identifying anomalies
- Retrieving historical RCA
- Applying business context
- Generating explainable RCA
- Recommending corrective actions
- Producing executive-ready summaries

---

# 4. High-Level Solution Architecture

User

↓

Frontend

↓

API Layer

↓

Workflow Orchestrator

↓

Planner Agent

↓

Data Validation Agent

↓

Analytics Agent

↓

Knowledge Retrieval Agent (RAG)

↓

Business Context Agent

↓

RCA Reasoning Agent

↓

Recommendation Agent

↓

Executive Summary Agent

↓

Validation Agent

↓

Governance Agent

↓

Response

---

# 5. Technology Stack

Recommended stack:

Backend
- Python 3.12+
- FastAPI

Frontend
- React
- TypeScript

Database
- PostgreSQL

Vector Database
- ChromaDB (or enterprise-approved alternative)

Authentication
- Enterprise SSO / OAuth / RBAC

Containerization
- Docker

CI/CD
- GitHub Actions / Azure DevOps / Enterprise CI platform

Monitoring
- OpenTelemetry
- Prometheus
- Grafana

Logging
- Structured JSON logging

---

# 6. Repository Structure

Recommended layout:

```
root/

docs/

src/

api/

agents/

analytics/

configuration/

models/

rag/

prompts/

services/

utilities/

tests/

deployment/

scripts/

assets/

README.md

CLAUDE.md
```

---

# 7. Documentation Hierarchy

Documentation is organized into the following categories:

Business Documentation

Architecture

AI Architecture

Analytics

Data

Prompt Engineering

RAG

Security

Governance

Operations

Deployment

Testing

Performance

Monitoring

Implementation

Reference

Every Markdown file represents a governed document and should be treated as a controlled artifact.

---

# 8. Build Order

Recommended implementation sequence:

1. Environment Setup
2. Configuration
3. Database
4. Vector Database
5. API Foundation
6. Analytics Engine
7. Knowledge Ingestion
8. RAG
9. AI Agents
10. Workflow Orchestrator
11. Prompt Library
12. Frontend
13. Testing
14. Monitoring
15. Security
16. Production Deployment

---

# 9. AI Agent Responsibilities

Planner

Plans execution.

Validation

Checks input quality.

Analytics

Calculates KPIs.

Knowledge Retrieval

Retrieves organizational knowledge.

Business Context

Applies operational context.

Reasoning

Generates RCA.

Recommendation

Suggests corrective actions.

Executive Summary

Produces leadership summary.

Validation

Reviews AI output.

Governance

Ensures compliance.

---

# 10. Business Rules

Important forecasting rules:

Forecast Error

Actual − Forecast

Forecast Variance

(Actual − Forecast)/Forecast

Forecast Adherence

1 − ABS((Actual − Forecast)/Forecast)

Critical Rule:

Forecast Variance determines forecast direction.

Forecast Adherence measures only forecast accuracy.

Never infer forecast direction using Forecast Adherence.

---

# 11. Coding Standards

Follow:

- Small functions
- Single responsibility
- Type hints
- Modular architecture
- Stateless services where practical
- Dependency injection
- Configuration over hardcoding

Never:

- Hardcode secrets
- Hardcode thresholds
- Duplicate business logic
- Ignore exceptions

---

# 12. Prompt Standards

All prompts must:

- Be version controlled
- Have Prompt IDs
- Include metadata
- Pass benchmark testing
- Follow Responsible AI guidelines

Prompt changes require formal review before production deployment.

---

# 13. Knowledge Management

Knowledge sources include:

- Historical RCA
- SOPs
- KPI documentation
- Business rules
- Lessons learned
- Governance documentation

Only approved knowledge may be indexed.

---

# 14. Security Principles

Always implement:

- RBAC
- Encryption
- Audit logging
- Secure APIs
- Secret management
- Input validation
- Output validation

---

# 15. Responsible AI Principles

The AI must:

- Be explainable
- Avoid hallucinations
- Cite retrieved knowledge where applicable
- Distinguish facts from assumptions
- Support human review
- Maintain transparency

---

# 16. Testing Strategy

Testing includes:

- Unit Tests
- Integration Tests
- API Tests
- AI Evaluation
- Security Tests
- Performance Tests
- Regression Tests
- User Acceptance Testing

---

# 17. Performance Targets

Target goals:

- API < 2 seconds
- RCA < 15 seconds
- Retrieval < 2 seconds
- Availability > 99.9%

Validate against business requirements before production.

---

# 18. Deployment Principles

Deployment should include:

- Automated CI/CD
- Versioning
- Health checks
- Rollback capability
- Monitoring
- Backup validation

---

# 19. Documentation Rules

Whenever functionality changes:

Update:

- Functional Requirements
- Technical Design
- API Documentation
- Prompt Library
- Configuration Reference
- Testing Documentation

Documentation is part of the deliverable.

---

# 20. AI Coding Assistant Guardrails

AI coding assistants should:

✔ Read architecture before writing code.

✔ Follow documented business rules.

✔ Preserve modular architecture.

✔ Reuse existing components.

✔ Respect coding standards.

✔ Update documentation when implementation changes.

AI coding assistants should NOT:

✘ Invent business rules.

✘ Change KPI formulas.

✘ Modify prompt behavior without version updates.

✘ Introduce undocumented dependencies.

✘ Remove governance controls.

✘ Bypass validation.

---

# 21. Definition of Done

A feature is complete only when:

- Code implemented.
- Unit tests pass.
- Integration tests pass.
- Documentation updated.
- Security reviewed.
- Performance acceptable.
- AI evaluation completed.
- Business validation completed.

---

# 22. Future Enhancements

Potential roadmap items:

- Predictive RCA
- Agent self-reflection
- Autonomous planning
- Knowledge graphs
- Multi-modal document ingestion
- Voice interaction
- Real-time streaming analytics
- Continuous learning workflows

---

# 23. Final Principles

The Forecast Adherence RCA Agent is designed as an enterprise-grade, AI-native decision support platform.

Every implementation decision should prioritize:

- Accuracy
- Explainability
- Governance
- Security
- Scalability
- Maintainability
- Business value

This repository should remain the single source of truth for all business, architectural, engineering, and operational knowledge related to the Forecast Adherence RCA Agent.

---

# End of Repository Guide