# LLM-Era Roadmap

> Goal: stay useful and in demand as software engineering shifts around LLMs.
> NOT training my own LLM — building production-grade systems on top of and around LLMs.
> Status: not started. Last updated: 2026-07-15.
> Suggested pace: 6-8 hours/week. Every phase ends with a concrete deliverable — watching videos doesn't count as progress.

## Phase 0 — Intuition: stop treating the LLM as a black box (weeks 1-4)

Goal: transformer, tokens, context, attention, why hallucinations happen — at an intuitive level.

- [ ] 3Blue1Brown neural network + transformer series (quick pass, ~3 hours)
- [ ] Karpathy "Zero to Hero": micrograd → makemore (first 2-3 videos) → **"Let's build GPT"** → the tokenizer video
- [ ] Mini project: train a small character-level model with nanoGPT (on the Mac or a rented single GPU, ~$10-20)
  - Fun variant: train on a Turkish corpus and watch how the output degrades
- [ ] Deliverable: a short note/post — "What I learned building GPT by hand"

## Phase 1 — Engineering with LLMs: the primitives (weeks 4-8, partly parallel with Phase 0)

Goal: build agent / tool-use / RAG systems at the raw-API level, no frameworks. **In Go** — extending existing strengths.

- [ ] Claude API fundamentals: messages, tool use, streaming, prompt caching (Anthropic docs + the "Building Effective Agents" post)
- [ ] Hand-rolled agent loop: "LLM + tools + loop" in Go, no framework — NO LangChain etc.
- [ ] Production hardening of the loop: rate limits + retry/backoff, timeouts, malformed/partial
      JSON from the model, structured output — the boring layer that separates demo from production
- [ ] MCP: write a simple MCP server with the Go SDK (any topic, warm-up exercise)
- [ ] RAG basics: embeddings, chunking, retrieval — one small experiment (e.g. Q&A over my own notes)
- [ ] Intro to evals: try promptfoo OR write my own assertion harness
      — shape the exercise like Phase 2's golden journeys (input + expected diagnosis) so it bridges directly
- [ ] Deliverable: a working minimal agent + MCP server in Go (on GitHub)

## Phase 2 — The real proof: an LLM layer on the entity-journey product (weeks 8-16)

Goal: be able to say "I built a production-grade, eval'd, instrumented LLM system" in my portfolio.
This phase runs as part of the OSS product plan (todo.md) — not a separate project.

- [ ] **Journey diagnosis assistant:** paste an ID → the LLM reads the timeline and explains
      the broken stage and likely cause in plain language (from error/error_code + stage history)
- [ ] **Backend as an MCP server:** expose the lookup API as MCP tools — users can plug it
      into their own Claude and ask "where did ORD-123 get stuck?"
      (also a product differentiator: nobody in the competitor table has it)
- [ ] **Eval set — the heart of the plan:** 20-30 golden journeys + expected diagnoses;
      mix of assertion-based + LLM-as-judge; runs in CI, catches regressions
- [ ] **Prompt injection & tool safety:** journey data is untrusted input — a hostile string in
      error_code/payload must not become instructions to the LLM. Treat data as data (delimit/escape),
      keep MCP tools read-only, red-team the assistant with a few poisoned journeys in the eval set
- [ ] **Context strategy:** long timelines won't fit the window — decide summarize/truncate/paginate
      up front as a design note, don't discover it in production
- [ ] **LLM observability:** token/cost/latency instrumentation — dogfooding my own product
- [ ] Deliverable: the LLM feature in the README + demo GIF; eval results as a table

## Phase 3 — Consistency and visibility (ongoing)

- [ ] AI-aided engineering mastery: use Claude Code systematically for design/review/exploration,
      not just code; keep growing my own skill/hook setup (already started)
- [ ] One post per phase: "A framework-free agent loop in Go", "Writing evals for an LLM feature",
      "Adding LLM diagnosis to an observability product" — HN / r/golang / blog
- [ ] Don't drop the fundamentals: distributed systems, debugging, design — the engineer who
      can't audit AI output is in the most fragile position
- [ ] Review this plan every 3 months (first check-in: October 2026)

## Traps

- **Course hoarding:** watching ≠ learning; every phase ends with a deliverable — don't move on without it.
- **Framework hype:** don't sink time into LangChain/LlamaIndex — primitives (API, tool use, MCP)
  last, frameworks churn. If a framework is ever needed, it's a one-day learn anyway.
- **Demos without evals:** an LLM feature that "seems to work" is worthless in a portfolio;
  the eval set is the real proof and the rarest skill in the market.
- **The fine-tune temptation:** no fine-tuning in this plan. Don't start until evals prove the need (v2+ topic).
- **Time conflict:** don't let this compete with the OSS product plan — Phase 2 is already an item
  in that plan; Phases 0-1 run on evening/weekend slots.

## Resources (short list — don't add more)

- Karpathy: Zero to Hero playlist, nanoGPT repo
- 3Blue1Brown: Neural networks series (transformer chapters)
- Anthropic: docs (tool use, MCP), "Building Effective Agents" post
- promptfoo (eval tool) — or my own harness
- Book (optional, along the way): Chip Huyen — *AI Engineering*
