# Anthropic Managed Agents Architecture

- Source: [[raw/sources/agent/engnieering/Scaling Managed Agents Decoupling the brain from the hands|Scaling Managed Agents]]
- Topics: [[wiki/topics/managed-agents]], [[wiki/topics/agent-harness-engineering]], [[wiki/topics/agent-memory-and-context]]
- Entities: [[wiki/entities/agent-engineering]], [[wiki/entities/agent-harness]], [[wiki/entities/agent-memory]]

## Core points

- Managed Agents decouples the agent brain, the session log, and the hands or sandboxes into separate interfaces.
- The design replaces fragile stateful containers with recoverable components that can be reprovisioned independently.
- Session history lives outside the model context window and can be reread selectively through the event log.
- Security improves when credentials stay outside the sandbox that runs model-generated code.
- Provisioning hands only when needed reduces time-to-first-token for many sessions.

## Why it matters

This source is a strong anchor for the wiki because it connects harness design, durability, sandbox security, and long-running context management.

## Source embed

![[raw/sources/agent/engnieering/Scaling Managed Agents Decoupling the brain from the hands]]
