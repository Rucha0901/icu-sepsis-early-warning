# Explainability & Model Governance

This document describes how ICU Sepsis Early Warning Agent reasons, evaluates evidence, and enforces operational boundaries without requiring examination of the underlying codebase.

## Decision Making Architecture and How It Decides Reasoning Pathways
ICU Sepsis Early Warning Agent reaches operational and technical determinations through an event-driven multi-agent consensus loop. The lead vitals-trend-analyzer agent evaluates domain telemetry and decides whether candidate interventions satisfy safety and performance thresholds. Before any strategic decision is finalized, the independent sofa-score-auditor agent audits the reasoning steps against invariant constraints. This dual-loop reasoning process ensures that every action is grounded in verified empirical evidence rather than speculative model generation.

## Inputs, Data Sources, and Contextual Data Used
The agent ingests real-time operational metrics, structured log records, and environmental configuration parameters as primary inputs. In addition to direct telemetry streams, the system incorporates version-controlled policies, baseline performance profiles, and regulatory criteria as external data sources. All raw input data used during diagnostic evaluation is processed in isolated execution memory with automated redaction of sensitive identifiers. System inputs undergo schema validation and cryptographic verification to prevent data poisoning and ensure auditability.

## Limitations, Operational Constraints, and Known Issues
A primary operational constraint of ICU Sepsis Early Warning Agent is that it executes strictly within designated domain boundaries and requires human authorization for irreversible system mutations. The agent enforces strict rate-limiting constraints and computational budget caps to prevent resource exhaustion during high-load events. Furthermore, a known issue in disconnected edge environments is that latency can temporarily degrade access to external reference catalogs. The agent is deliberately designed to abstain from speculative conclusions when data quality metrics fail to satisfy confidence requirements.
