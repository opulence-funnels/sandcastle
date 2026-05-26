---
"@ai-hero/sandcastle": patch
---

`copilot()` agent provider now parses the `copilot --output-format json` JSONL stream. Text deltas (`assistant.message_delta`), `bash` tool calls (`tool.execution_start`), the final assistant message (`assistant.message`), and the session id (terminal `result` event) are surfaced as `StreamEvent`s, so the Orchestrator's `result.stdout`, `logging.onAgentStreamEvent` timeline, and stderr-empty error fallback now work for Copilot the same as they do for Claude Code, Codex, and Pi. Previously `parseStreamLine` was a no-op.
