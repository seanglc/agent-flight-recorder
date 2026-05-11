# Two-Minute Demo Script

## 0:00 - 0:15

AI agents are starting to touch real enterprise systems: code repositories, email, documents, APIs, and payments. The problem is that security teams often cannot reconstruct what happened after an agent run.

## 0:15 - 0:35

This is Agent Flight Recorder. It turns an AI-agent transcript, tool log, or Lobster Trap-style audit stream into a security audit trail. The default run shows an adversarial agent workflow: prompt injection, sensitive file access, exfiltration, and dangerous shell commands.

## 0:35 - 1:00

The system immediately returns a DENY decision with a critical risk score. It flags prompt injection, exfiltration, sensitive paths, dangerous commands, and missing approval. Any credential-like value is redacted before it appears in copied or downloaded reports.

## 1:00 - 1:25

The timeline shows exact evidence rows by transcript line. This matters for enterprise review because a compliance team needs to know not only that something was risky, but where it happened and what control fired.

## 1:25 - 1:45

The brief tab turns the trace into an executive remediation plan: deny sensitive filesystem access, quarantine exfiltration attempts, block dangerous shell commands, and require approval before high-impact actions.

## 1:45 - 2:00

Finally, the Lobster Log sample shows the sponsor fit: inline DENY and QUARANTINE events become a readable incident brief. The policy tab exports a starter pack for hardening the next run. The goal is concrete governance: every agent run gets a risk decision, evidence trail, redaction, and policy update path.
