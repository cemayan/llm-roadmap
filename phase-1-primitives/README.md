# Phase 1 — Engineering with LLMs: the primitives (weeks 4-8)

Goal: agent / tool-use / RAG at the raw-API level, **in Go**, no frameworks.

**Deliverable:** a working minimal agent + MCP server in Go, published on GitHub.

## Checklist

- [ ] Claude API fundamentals: messages, tool use, streaming, prompt caching
      (Anthropic docs + "Building Effective Agents" post) → notes in `claude-api-notes.md`
- [ ] Hand-rolled agent loop in Go: LLM + tools + loop → `agent-loop/`
- [ ] Production hardening of the loop: rate limits + retry/backoff, timeouts,
      malformed/partial JSON, structured output
- [ ] Simple MCP server with the Go SDK (any topic, warm-up) → `mcp-server/`
- [ ] RAG basics: embeddings, chunking, retrieval — Q&A over my own notes → `rag-experiment/`
- [ ] Intro to evals: promptfoo OR my own assertion harness → `evals/`
      — shape it like Phase 2's golden journeys (input + expected diagnosis)
- [ ] Publish agent + MCP server to GitHub

Each sub-project gets its own Go module (`go mod init`) when started.
