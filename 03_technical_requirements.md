# Technical Requirements

## Goal

Build a system that sits above existing engineering tools and creates a structured history of technical reasoning.

## Initial Integrations

### Jira

Use Jira to understand:

- project;
- ticket;
- task description;
- status;
- comments;
- sprint context.

The system should link attempts to the Jira issue they relate to.

### GitHub

Use GitHub to capture:

- commits;
- branches;
- Pull Requests;
- PR comments;
- code changes;
- issue references.

GitHub should provide evidence for what eventually became part of the codebase.

### Local Development

This is the key differentiator.

The system should eventually be able to observe selected local development activity such as:

- Git diffs;
- local branches;
- test results;
- terminal commands;
- experiment outputs;
- notebooks;
- AI coding sessions.

It should **not record everything blindly**.

Only meaningful changes or attempts should become project knowledge.

---

## Suggested Architecture

```text
Jira ───────────┐
GitHub ─────────┤
Slack / Teams ──┤
Documents ──────┤
Local Dev ──────┼──► Reasoning Engine
Experiments ────┘           │
                             ▼
                      Reasoning Store
                             │
                             ▼
                    Search / Timeline UI
```

## Data Model

A basic attempt record could contain:

```text
problem_id
attempt_id
title
description
status
reason
evidence
constraints
created_at
created_by
revisit_condition
linked_jira_ticket
linked_git_commit
linked_pull_request
```

## MVP

The first version should support:

1. Creating a problem.
2. Adding attempts.
3. Marking attempts as adopted, rejected, or shelved.
4. Recording why the status changed.
5. Linking attempts to Jira and GitHub.
6. Viewing attempts in a timeline.
7. Searching previous attempts.

## Later Features

Possible future capabilities:

- VS Code extension;
- Jira plugin;
- GitHub App;
- Slack / Teams integration;
- automatic detection of major code-direction changes;
- AI-generated summaries of reasoning;
- automatic extraction of evidence;
- project knowledge graph;
- presentation / stakeholder summary generation.

## Important Constraints

The system must consider:

- developer privacy;
- company source-code security;
- confidential information;
- permission controls;
- avoiding excessive monitoring;
- false AI assumptions about why a developer changed direction.

Human confirmation should remain part of important decisions.
