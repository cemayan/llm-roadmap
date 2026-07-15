# Phase 2 — LLM layer on the entity-journey product (weeks 8-16)

**The work itself lives in the OSS product repo / plan (`workspace/todo.md`) — this
folder only tracks status and cross-links, to avoid duplicating the plan.**

Goal: "I built a production-grade, eval'd, instrumented LLM system" in the portfolio.

## Checklist (mirrors ROADMAP.md — tick here, build there)

- [ ] Journey diagnosis assistant: ID → LLM reads timeline, explains broken stage + likely cause
- [ ] Backend as an MCP server: lookup API as MCP tools ("where did ORD-123 get stuck?")
- [ ] Eval set — the heart: 20-30 golden journeys + expected diagnoses,
      assertion-based + LLM-as-judge, runs in CI
- [ ] Prompt injection & tool safety: journey data is untrusted input — delimit/escape,
      read-only MCP tools, poisoned journeys in the eval set
- [ ] Context strategy: long timelines vs. the window — summarize/truncate/paginate
      decided as a design note up front
- [ ] LLM observability: token/cost/latency instrumentation (dogfooding)
- [ ] Deliverable: LLM feature in README + demo GIF; eval results table
