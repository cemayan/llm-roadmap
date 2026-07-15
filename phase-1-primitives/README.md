# Phase 1 — Engineering with LLMs: the primitives (weeks 4-8)

Goal: agent / tool-use / RAG at the raw-API level, **in Go**, no frameworks.

**Deliverable:** a working minimal agent + MCP server in Go, published on GitHub.

## First session setup (5 min)

- Anthropic Console → API key + a few dollars of credit; `export ANTHROPIC_API_KEY=...`
- `mkdir agent-loop && cd agent-loop && go mod init && go get github.com/anthropics/anthropic-sdk-go`
- First target: one message → one tool call → loop until `stop_reason != tool_use`

## Checklist

- [ ] Claude API fundamentals: messages, tool use, streaming, prompt caching
      (Anthropic docs + "Building Effective Agents" post) → notes in `claude-api-notes.md`
- [ ] Hand-rolled agent loop in Go: LLM + tools + loop → `agent-loop/`
- [ ] Production hardening of the loop: rate limits + retry/backoff, timeouts,
      malformed/partial JSON, structured output
- [ ] Simple MCP server with the Go SDK (any topic, warm-up) → `mcp-server/`
- [ ] RAG basics: embeddings, chunking, retrieval — Q&A over my own notes → `rag-experiment/`
      — keep it dumb: any embedding API + in-memory/SQLite + hand-rolled cosine.
      No vector DB until the dumb version demonstrably falls short.
- [ ] Intro to evals: promptfoo OR my own assertion harness → `evals/`
      — shape it like Phase 2's golden journeys (input + expected diagnosis)
- [ ] Publish agent + MCP server to GitHub

Each sub-project gets its own Go module (`go mod init`) when started.
