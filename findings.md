# Alpha feedback - building prompt agents on Pollinations

Findings from building and testing the three agents in this repo (quests #14821, #14822, #14823).

## 1. Computer MCP: `/tmp` is wiped after every call

Memory agents must not store state under `/tmp` - files there are deleted after every tool call, so nothing survives into the next conversation. The persistent tree is `/workspace/`. This is documented in the computer-mcp README, but it is easy to miss when writing an agent prompt; our first mnemo version silently "forgot" everything between chats because of it.

Suggestion: mention this gotcha in BUILD_YOUR_OWN_AGENT.md next to the `computer` MCP server entry - it is the natural first place agent authors look.

## 2. Identical requests return cached responses

Sending the exact same chat-completions body to a managed agent returns the cached earlier response (same tool-call ids, same stale tool results). When testing stateful agents (memory, games) this looks like the agent is broken: our "what do you remember?" re-check replayed an old empty read. Varying any part of the message bypasses it.

Suggestion: a `no-cache`-style request option, or a note in the Community Agents API docs, would save debugging time.

## 3. Minor: agent updates apply cleanly via CLI

`polli agents update <id> --config agent.json` replaced the system prompt and MCP servers without downtime - worked well. The `agents get` table column `pollinations_tools` only reflects the `pollinations` MCP server, which initially looked like our `computer` server had not been attached (it had - visible via `--json`). A `mcp_servers` column or a clearer label would avoid that confusion.
