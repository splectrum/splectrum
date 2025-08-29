# Inbox/Outbox Pattern for Event-Driven Choreography

## Overview

Each repository implements an inbox/outbox pattern for asynchronous, event-driven communication between components.

## Pattern Structure

```
inbox/              # Incoming items to process
  README.md         # Processing instructions
outbox/             # Outgoing items for other repos
  README.md         # Content requirements & template
```

## Key Principles

1. **No History**: Items are deleted after processing (audit log maintains history)
2. **Self-Contained Events**: Each item includes all context, actions, and quality gates
3. **Executable Specifications**: Items are ready for AI/automation consumption
4. **Event-Driven**: Items trigger appropriate responses in target repositories
5. **Single Concern Repos**: Enable natural serialization of work

## Naming Convention

`YYYY-MM-DD_TARGET-ORG_TARGET-REPO_ITEM-TYPE_DESCRIPTION.md`

## Benefits

- **Decoupled Communication**: Repos don't need direct dependencies
- **AI-Friendly**: Clear specifications with quality gates
- **Audit Trail**: Processing logged, items deleted
- **P2P Ready**: No central coordination required

This pattern enables true event-driven choreography where components respond autonomously to well-defined events.