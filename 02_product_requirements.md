# Product Requirements

## Main Requirement

The system must allow a team to understand **how a technical solution evolved over time**.

## Core Objects

Each project should contain:

### Problem
What is being solved?

### Attempt
What approach was tried?

### Evidence
What happened during testing or implementation?

### Outcome
An attempt can be:

- Adopted
- Rejected
- Shelved
- Superseded
- In Progress

### Reason
Why did the outcome occur?

### Revisit Condition
When could this approach become useful again?

---

## Core Features

### 1. Attempt History

Users should be able to see the sequence of approaches taken for a problem.

Example:

**Approach A → Rejected**  
**Approach B → Shelved**  
**Approach C → Adopted**

### 2. Link Evidence

An attempt should be able to link to evidence such as:

- Jira tickets;
- GitHub commits;
- Pull Requests;
- experiment outputs;
- notebooks;
- test results;
- documents;
- meeting notes;
- Slack / Teams messages.

### 3. Capture Unpublished Work

The system should support recording work that never reached GitHub or Jira.

For example:

- local experiments;
- failed implementations;
- temporary branches;
- prototype code;
- AI coding conversations;
- test failures.

### 4. Human Confirmation

The system should not automatically assume why something changed.

It should be able to suggest:

> "It looks like Approach A was replaced by Approach B. Why?"

The developer can confirm the reason.

### 5. Search

Users should be able to ask questions such as:

- Why are we using this architecture?
- What approaches did we try before this?
- Why was Approach B abandoned?
- Did this fail technically or was it deprioritised?
- What should we reconsider if constraints change?

### 6. Timeline

Each problem should have a simple chronological reasoning timeline.

## Design Principle

The system should require **very little manual documentation**.

Capturing project knowledge should feel like part of development, not another administrative task.
