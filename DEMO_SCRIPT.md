# Two-Minute Demo Script

## 0:00 - 0:15

AI agents are starting to touch real enterprise systems: code repositories, email, documents, APIs, and payments. The problem is that security teams often cannot reconstruct what happened after an agent run.

## 0:15 - 0:35

This is Agent Flight Recorder. It turns an AI-agent transcript or tool log into a security audit trail. I am loading a realistic run where a user asked an agent to find a bounty, the agent touched GitHub, and a credential was exposed.

## 0:35 - 1:00

The system immediately returns a DENY decision with a critical risk score. It flags economic action, external writes, missing approval, and credential exposure. The token is redacted before it appears in the audit output.

## 1:00 - 1:25

The timeline shows exact evidence rows by transcript line. This matters for enterprise review because a compliance team needs to know not only that something was risky, but where it happened and what control fired.

## 1:25 - 1:45

The brief tab turns the trace into an executive remediation plan: rotate exposed credentials, require approval before GitHub or email writes, and route payment or bounty actions to human review.

## 1:45 - 2:00

Finally, the policy tab exports a Lobster Trap-style policy pack. The goal is to make agent security review concrete: every run gets a risk decision, evidence trail, redaction, and policy update path.
