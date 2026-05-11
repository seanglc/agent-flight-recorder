# Agent Flight Recorder

## Short Description

AI agent audit trails: detect risky tool use, leaked secrets, prompt injection, and missing human approval.

## Long Description

Agent Flight Recorder is an enterprise governance prototype for teams that want to deploy AI agents into real workflows without losing control of what those agents do.

Modern agents can read files, call APIs, push code, open pull requests, send messages, and trigger business actions. That creates a security and compliance problem: after an agent run, teams need to know what happened, which actions were risky, which secrets were exposed, which policy controls fired, and where human approval should have been required.

Agent Flight Recorder turns an agent transcript, tool log, or Lobster Trap-style JSONL audit stream into a regulator-readable audit package. It flags credential exposure, prompt injection, exfiltration patterns, sensitive file access, dangerous commands, external writes, financial actions, and missing approval checkpoints. It then generates a risk score, evidence timeline, executive remediation brief, and policy-hardening pack.

The prototype is intentionally practical: paste a transcript or load a policy audit log, click Analyze, and get an audit trail that a security, legal, or compliance team can review.

## Track

Track 1: Agent Security & AI Governance.

## Why It Fits

The Veea challenge asks for guardrails, observability, access control, audit tooling, red-team tooling, and enterprise security workflows for AI agents. Agent Flight Recorder focuses on the audit and governance layer:

- Observability over agent runs and tool calls
- Policy decisions such as ALLOW, DENY, HUMAN_REVIEW, and QUARANTINE
- Evidence rows with line-level traceability
- Redaction of leaked secrets before reports are copied or exported
- Lobster Trap-style JSONL audit event ingestion
- A policy pack that can be adapted into Lobster Trap rules
- A concrete approval-gate story for external writes and financial actions

## Demo Scenario

The default demo uses a clear adversarial workflow:

1. A user tries prompt injection.
2. The run references a sensitive SSH key path.
3. The agent prepares a dangerous shell command.
4. The agent attempts to exfiltrate secrets to an external destination.

Agent Flight Recorder flags the run as critical because it includes prompt injection, sensitive file access, exfiltration, dangerous commands, and missing approval checkpoints.

A second "Lobster Log" sample demonstrates the sponsor fit: inline DENY and QUARANTINE events from a policy proxy become a human-readable incident brief and policy-hardening queue.

## Technologies

- Browser-only HTML, CSS, and JavaScript prototype
- Local deterministic risk engine
- JSONL policy-audit event parser
- Secret redaction before export
- Markdown audit report export
- Lobster Trap-style policy concepts

## Tags

AI Governance, Agent Security, Audit Trail, Prompt Injection, Secret Detection, Enterprise AI, Lobster Trap, Compliance, Human Review, Agent Observability.

## Judging Notes

Business value: Enterprises need proof, not vibes, before agents can operate in production systems. This prototype gives security and compliance teams an audit package for every agent run.

Originality: Inline guardrails are necessary, but they are not the whole governance workflow. Agent Flight Recorder focuses on the post-run artifact: what the agent saw, what it did, what was risky, what was redacted, which inline policy event fired, and what policy should happen next.

Presentation: The app is built for a simple live demo. Load the default run, show the DENY decision, walk the timeline, switch to the Lobster Log sample, then export the policy pack.

Technical value: The rules are deterministic and auditable, matching enterprise expectations and aligning with Lobster Trap's non-LLM inspection approach.
