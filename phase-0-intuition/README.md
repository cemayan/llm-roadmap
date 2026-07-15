# Phase 0 — Intuition (weeks 1-4)

Goal: transformer, tokens, context, attention, why hallucinations happen — intuitively.

**Deliverable:** a short note/post — "What I learned building GPT by hand" → `gpt-by-hand.md`

## Checklist

- [ ] 3Blue1Brown neural network + transformer series (quick pass, ~3h) → notes in `3b1b-notes.md`
- [ ] Karpathy Zero to Hero: micrograd → makemore (first 2-3) → "Let's build GPT" → tokenizer video
      → notes in `karpathy-notes.md`
- [ ] nanoGPT mini project: char-level model → `nanogpt-experiment/`
  - Runs fine on the MacBook (M4 Pro): PyTorch with `--device=mps`, char-level
    Shakespeare config trains in minutes-to-hours. No GPU rental needed —
    the goal is intuition, not a good model.
  - Fun variant: Turkish corpus, watch output degrade
- [ ] Write the deliverable post
