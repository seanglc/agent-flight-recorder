# Two-Minute Demo Script

## 0:00 - 0:15

I asked an AI coding agent to find a bounty-like task. It pushed code, opened a pull request, interacted with review bots, and then a credential-like token was accidentally pasted into the run. The problem was obvious: after an agent touches real systems, security teams need a clean record of what happened.

## 0:15 - 0:35

This is Agent Flight Recorder. Lobster Trap is the inline control layer; AFR is the audit and policy-update layer downstream of it. The default run shows an adversarial workflow: prompt injection, sensitive file access, exfiltration, and dangerous shell commands.

## 0:35 - 1:00

The system immediately returns a DENY decision with a critical risk score. It flags prompt injection, exfiltration, sensitive paths, dangerous commands, and missing approval. Any credential-like value is redacted before it appears in copied or downloaded reports.

## 1:00 - 1:25

The timeline shows exact evidence rows by transcript line. This matters for enterprise review because a compliance team needs to know not only that something was risky, but where it happened and what control fired.

## 1:25 - 1:45

The Executive Summary turns the trace into a remediation plan: deny sensitive filesystem access, quarantine exfiltration attempts, block dangerous shell commands, and require approval before high-impact actions. It also shows the policy update loop back into Lobster Trap.

## 1:45 - 2:00

Finally, the Lobster Log sample shows the sponsor fit: inline DENY and QUARANTINE events become a readable incident brief. The Lobster Trap Policy tab exports a starter pack for hardening the next run. The goal is concrete governance: every agent run gets a risk decision, evidence trail, redaction, and policy update path.
