# Agent Flight Recorder

Hackathon prototype for lablab.ai Transforming Enterprise Through AI, Track 1: Agent Security & AI Governance.

Agent Flight Recorder reviews AI-agent transcripts and tool logs for enterprise governance signals:

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

## Run

Open `index.html` in a browser.

No build step is required.

## Files

- `index.html` - interactive browser demo
- `SUBMISSION.md` - lablab project copy
- `DEMO_SCRIPT.md` - two-minute video script
- `sample-runs/` - benign and adversarial input examples
- `policy-pack/lobstertrap_agent_flight_recorder.yaml` - starter policy pack
- `assets/cover.png` - hackathon cover image

## Hackathon Positioning

Enterprise teams are beginning to let agents read files, call APIs, send messages, and update production systems. The hard problem is not only blocking obviously bad prompts. It is proving what the agent saw, what it did, which control fired, what was redacted, and where human approval was required.

Agent Flight Recorder turns agent traces into an audit artifact a security, legal, or compliance team can actually review.

## Lobster Trap Fit

The prototype mirrors Lobster Trap's policy model:

- `DENY` for credential leaks, prompt injection, dangerous commands, and sensitive paths
- `QUARANTINE` for exfiltration patterns
- `HUMAN_REVIEW` for external writes and economic actions
- `LOG` for routine tool usage and baseline observability

The generated policy panel uses the same broad YAML concepts as Lobster Trap: `ingress_rules`, `egress_rules`, `conditions`, `risk_score`, `contains_credentials`, `contains_injection_patterns`, `contains_exfiltration`, and actions such as `DENY`, `HUMAN_REVIEW`, and `QUARANTINE`.

## Submission Checklist

- Create solo team on lablab.ai
- Upload `assets/cover.png` as cover image
- Publish this folder to a public GitHub repository
- Host the static demo with GitHub Pages, Netlify, Vercel, or any static host
- Record a short demo using `DEMO_SCRIPT.md`
- Submit title, description, repo URL, demo URL, slides, and video
