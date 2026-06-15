# IncidentOS Product Requirements Document

Document ID: PRD-001
Version: 1.0
Status: Approved
Owner: Product & Engineering
Last Updated: 2026-06-16

## Executive Summary

IncidentOS is an evidence-first incident investigation platform designed to help software engineers investigate production incidents faster.

### Product Thesis

Observability solved visibility.

It did not solve investigation.

Evidence represents facts.
Investigations represent interpretations.

The platform follows the workflow:

Alert -> Incident -> Evidence -> Investigation -> Knowledge -> Future Investigation

## Vision

Enable engineering teams to move from alerts to understanding with minimal investigation effort.

## Mission

Help software engineers investigate production incidents faster through evidence-based investigations.

## Product Category

Evidence-First Incident Investigation Platform

## Primary User

Software Engineers investigating production incidents.

## Core Principles

- Investigation-Centric Design
- Evidence Before Reasoning
- Human-In-The-Loop
- Knowledge Accumulation
- Facts Over Interpretation

## Non Goals

- Multi-Tenancy
- Billing Systems
- Governance Workflows
- Compliance Management
- Automated Remediation
- Workflow Engines
- Enterprise IAM Platforms
- Policy Engines

# Functional Requirements

## Domain 1: Alert Management

Alerts are the primary entry point into the IncidentOS workflow.

### Requirements

- Accept authenticated webhook alerts
- Validate webhook signatures
- Deduplicate repeated alerts
- Maintain alert history
- Support manual alert creation

## Domain 2: Incident Management

Incidents are the central aggregate of the system.

### Severity Model

- P1 Critical
- P2 High
- P3 Medium
- P4 Low

### Lifecycle

Open -> Investigating -> Mitigated -> Resolved -> Closed

### Requirements

- Create incidents from alerts
- Support manual incident creation
- Assign incident ownership
- Change severity
- Record all state transitions
- Maintain complete incident history
- Support resolution and closure workflows

## Domain 3: Evidence Management

Evidence packages represent facts.

### Principles

- Immutable
- Versioned
- Traceable
- Source-attributed

### Requirements

- Generate evidence packages
- Normalize collected evidence
- Version evidence packages
- Preserve package history
- Inspect evidence packages
- Track provenance
- Regenerate evidence packages
- Record generation failures

## Domain 4: Investigation Management

Investigations represent interpretations derived from evidence.

### Confidence Levels

- Low
- Medium
- High

### Requirements

- Generate investigations from evidence
- Link findings to supporting evidence
- Generate summaries
- Generate findings
- Generate hypotheses
- Generate recommendations
- Assign confidence levels
- Require human approval
- Support rejection and regeneration

## Domain 5: Knowledge Management

Knowledge improves future investigations.

### Knowledge Types

- Runbooks
- Postmortems
- Lessons Learned

### Requirements

- Create postmortems from incidents
- Create lessons learned from investigations
- Manage runbooks
- Search knowledge assets
- Reference knowledge during investigations
- Track knowledge usage

## Domain 6: Timeline Management

Timeline is derived from domain events.

### Requirements

- Record incident events
- Record evidence events
- Record investigation events
- Provide chronological timelines
- Support audit-grade reconstruction

## Domain 7: User Management

### Roles

- Viewer
- Engineer
- Admin

### Requirements

- Support RBAC
- Restrict administrative actions
- Audit privileged operations

## Domain 8: Auditability

### Requirements

- Record all state transitions
- Record investigation approvals
- Record evidence generation activities
- Preserve audit history
