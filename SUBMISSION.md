# Agent Flight Recorder

## Short Description

AI agent audit trails: detect risky tool use, leaked secrets, prompt injection, and missing human approval.

## Long Description

Agent Flight Recorder is an enterprise governance prototype for teams that want to deploy AI agents into real workflows without losing control of what those agents do.

Modern agents can read files, call APIs, push code, open pull requests, send messages, and trigger business actions. That creates a security and compliance problem: after an agent run, teams need to know what happened, which actions were risky, which secrets were exposed, which policy controls fired, and where human approval should have been required.

Agent Flight Recorder turns an agent transcript or tool log into a regulator-readable audit package. It flags credential exposure, prompt injection, exfiltration patterns, sensitive file access, dangerous commands, external writes, financial actions, and missing approval checkpoints. It then generates a risk score, evidence timeline, executive remediation brief, and Lobster Trap-style policy pack.

The prototype is intentionally practical: paste a transcript, click Analyze, and get an audit trail that a security, legal, or compliance team can review.

## Track

Track 1: Agent Security & AI Governance.

## Why It Fits

The Veea challenge asks for guardrails, observability, access control, audit tooling, red-team tooling, and enterprise security workflows for AI agents. Agent Flight Recorder focuses on the audit and governance layer:

- Observability over agent runs and tool calls
- Policy decisions such as ALLOW, DENY, HUMAN_REVIEW, and QUARANTINE
- Evidence rows with line-level traceability
- Redaction of leaked secrets before reports are copied or exported
- A policy pack that can be adapted into Lobster Trap rules
- A concrete approval-gate story for external writes and financial actions

## Demo Scenario

The default demo uses a realistic agent workflow:

1. A user asks an AI agent to make money.
2. The agent finds a bounty-like task and interacts with GitHub.
3. A GitHub token is pasted into the conversation.
4. The agent pushes code, opens a pull request, comments externally, and later stops when an eligibility bot closes the PR.

Agent Flight Recorder flags the run as high risk because it includes economic action, external writes, credential exposure, and missing approval checkpoints.

## Technologies

- Browser-only HTML, CSS, and JavaScript prototype
- Local deterministic risk engine
- Secret redaction before export
- Markdown audit report export
- Lobster Trap-compatible policy concepts

## Tags

AI Governance, Agent Security, Audit Trail, Prompt Injection, Secret Detection, Enterprise AI, Lobster Trap, Compliance, Human Review, Agent Observability.

## Judging Notes

Business value: Enterprises need proof, not vibes, before agents can operate in production systems. This prototype gives security and compliance teams an audit package for every agent run.

Originality: Most guardrail demos stop at blocking a prompt. Agent Flight Recorder focuses on the whole operational trace: what the agent saw, what it did, what was risky, what was redacted, and what policy should happen next.

Presentation: The app is built for a simple live demo. Load the default run, show the DENY decision, walk the timeline, then export the policy pack.

Technical value: The rules are deterministic and auditable, matching enterprise expectations and aligning with Lobster Trap's non-LLM inspection approach.
