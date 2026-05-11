# Agent Flight Recorder

Hackathon prototype for lablab.ai Transforming Enterprise Through AI, Track 1: Agent Security & AI Governance.

Agent Flight Recorder is the post-run audit layer for AI agents. It reviews raw agent transcripts, tool logs, and Lobster Trap-style JSONL audit events for enterprise governance signals:

- leaked secrets or credential-like strings
- prompt injection and exfiltration attempts
- external writes such as GitHub pushes, comments, deployment, or email actions
- financial or bounty-seeking autonomy
- sensitive file paths and dangerous commands
- missing human approval checkpoints

The app produces:

- risk score and policy decision
- line-level audit timeline
- executive remediation brief
- Lobster Trap-compatible policy pack draft
- redacted markdown audit report
- JSONL audit-log ingestion for inline policy events

## Run

Open `index.html` in a browser.

No build step is required.

## Files

- `index.html` - interactive browser demo
- `SUBMISSION.md` - lablab project copy
- `DEMO_SCRIPT.md` - two-minute video script
- `sample-runs/` - benign, adversarial, and Lobster Trap audit-log examples
- `policy-pack/lobstertrap_agent_flight_recorder.yaml` - starter policy pack
- `assets/cover.png` - hackathon cover image

## Hackathon Positioning

Enterprise teams are beginning to let agents read files, call APIs, send messages, and update production systems. Inline controls such as Lobster Trap can block or quarantine risky requests. The next problem is proving what happened after the run: what the agent saw, what it tried to do, which control fired, what was redacted, and where human approval was required.

Agent Flight Recorder turns those traces into an audit artifact a security, legal, or compliance team can actually review.

## Lobster Trap Fit

The prototype is designed to sit downstream of Lobster Trap:

- It can ingest line-oriented agent traces for demos and investigation.
- It can also ingest JSONL audit events with fields like `request_id`, `direction`, `action`, `matched_rule`, and `metadata`.
- It turns inline policy events into a readable incident brief, evidence table, and policy-hardening queue.
- It generates a starter policy pack that follows Lobster Trap's ALLOW, DENY, HUMAN_REVIEW, QUARANTINE, ingress, egress, and metadata-condition vocabulary.

The local deterministic analyzer uses the same broad policy decisions:

- `DENY` for credential leaks, prompt injection, dangerous commands, and sensitive paths
- `QUARANTINE` for exfiltration patterns
- `HUMAN_REVIEW` for external writes and economic actions
- `LOG` for routine tool usage and baseline observability

The generated policy panel uses YAML concepts such as `ingress_rules`, `egress_rules`, `conditions`, `risk_score`, `contains_credentials`, `contains_injection_patterns`, `contains_exfiltration`, and actions such as `DENY`, `HUMAN_REVIEW`, and `QUARANTINE`.

## Demo Flow

The public demo opens on the adversarial run because it is the clearest 60-second story: prompt injection, sensitive file access, exfiltration, dangerous shell commands, and missing approval. The Lobster Log sample shows the stronger sponsor fit: inline policy events become a human-readable audit package.

## Submission Checklist

- Create solo team on lablab.ai
- Upload `assets/cover.png` as cover image
- Publish this folder to a public GitHub repository
- Host the static demo with GitHub Pages, Netlify, Vercel, or any static host
- Record a short demo using `DEMO_SCRIPT.md`
- Submit title, description, repo URL, demo URL, slides, and video
