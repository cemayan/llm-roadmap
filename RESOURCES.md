# Resources — direct links

The roadmap's short list, resolved to actual URLs so starting a session costs zero searching.
**Rule: don't add new resources here.** If something feels missing, it probably isn't — finish the deliverable first.

## Phase 0 — Intuition

- 3Blue1Brown, Neural networks series (incl. transformer/attention chapters):
  https://www.3blue1brown.com/topics/neural-networks
  (YouTube playlist: https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi)
- Karpathy, "Neural Networks: Zero to Hero": https://karpathy.ai/zero-to-hero.html
- nanoGPT: https://github.com/karpathy/nanoGPT

## Phase 1 — Primitives (Go)

- Claude API docs (messages, streaming, prompt caching): https://platform.claude.com/docs
  - Tool use: https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview
- Anthropic, "Building Effective Agents": https://www.anthropic.com/engineering/building-effective-agents
- Anthropic Go SDK: https://github.com/anthropics/anthropic-sdk-go
- Model Context Protocol: https://modelcontextprotocol.io
  - MCP Go SDK: https://github.com/modelcontextprotocol/go-sdk
- promptfoo (evals): https://www.promptfoo.dev — https://github.com/promptfoo/promptfoo

## Gap-review items (added 2026-07-15)

Production hardening (Phase 1):
- Errors & retry guidance: https://platform.claude.com/docs/en/api/errors
  (Go SDK auto-retries 429/5xx with backoff — `option.WithMaxRetries`)
- Rate limits: https://platform.claude.com/docs/en/api/rate-limits
- Structured outputs (schema-enforced JSON, kills the malformed-JSON class):
  https://platform.claude.com/docs/en/build-with-claude/structured-outputs
- Streaming (avoids HTTP timeouts on long outputs):
  https://platform.claude.com/docs/en/build-with-claude/streaming

Prompt injection & tool safety (Phase 2):
- OWASP Top 10 for LLM Applications (LLM01 = prompt injection):
  https://owasp.org/www-project-top-10-for-large-language-model-applications/
- Simon Willison's prompt injection series (canonical, readable):
  https://simonwillison.net/tags/prompt-injection/
- Tool use security notes (client-side tools, untrusted input):
  https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview

Context strategy (Phase 2):
- Context windows & token management:
  https://platform.claude.com/docs/en/build-with-claude/context-windows
- Compaction (server-side summarization for long histories):
  https://platform.claude.com/docs/en/build-with-claude/compaction
- Token counting (size the timeline before sending):
  https://platform.claude.com/docs/en/build-with-claude/token-counting

## Along the way (optional)

- Chip Huyen, *AI Engineering* (O'Reilly, 2025):
  https://www.oreilly.com/library/view/ai-engineering/9781098166298/
