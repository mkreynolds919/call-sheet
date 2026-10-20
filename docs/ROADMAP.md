# Roadmap

**Current phase:** 0 · Foundations (Oct 12 – Oct 25, 2026)

v1 target: a deployed play-calling assistant used by at least one real coach by August 2027.
Weekly progress is in the [build log](../log/). Key decisions are in [`docs/adr`](adr/).

---

## Phase 0 · Foundations
*Oct 12 – Oct 25, 2026*

- [x] Public repo with README, license, and `docs/adr` folder
- [ ] Python environment (`uv`) with `nflreadpy` and `polars`
- [ ] 2016–2025 play-by-play loaded and stored as Parquet
- [ ] EPA by down and distance, computed and charted
- [ ] Play families defined from available columns, with known gaps written down
- [ ] Problem statement: target, features, and the selection-bias limitation

## Phase 1 · Situational recommender
*Oct 26 – Dec 6, 2026*

- [ ] Feature pipeline for game state
- [ ] Baseline model (situational averages)
- [ ] Gradient-boosted model (LightGBM) compared against the baseline
- [ ] Evaluation on held-out seasons, with calibration checks
- [ ] Similar-situation lookup with sample sizes and uncertainty
- [ ] Writeup: why naive play-type EPA misleads

## Phase 2 · Backend and first deploy
*Dec 14, 2026 – Jan 17, 2027*

- [ ] FastAPI service serving recommendations
- [ ] Postgres schema
- [ ] Docker build and GitHub Actions CI
- [ ] AWS infrastructure in Terraform
- [ ] Billing alarm and cost notes

> **Gate:** recommender API live on a public URL

## Phase 3 · Playbook retrieval
*Jan 18 – Mar 14, 2027*

- [ ] Structured play entry (name, formation, concept, tags)
- [ ] Embeddings stored in pgvector
- [ ] Hybrid keyword + vector search
- [ ] LLM explanation with citations and schema-validated output
- [ ] Retrieval evaluation set and metrics

## Phase 4 · Security and evals
*Mar 15 – Apr 18, 2027*

- [ ] Authentication and per-team row-level security
- [ ] Threat model document
- [ ] Prompt-injection test suite (malicious playbook uploads)
- [ ] Retrieval and faithfulness evals running in CI
- [ ] Rate limiting

> **Gate:** eval set of 50+ queries and the attack suite pass in CI

## Phase 5 · Sideline logger and tendencies
*Apr 19 – May 30, 2027*

- [ ] Mobile-first play logging UI
- [ ] Self-scout and opponent tendency reports
- [ ] Team-specific adjustment shrunk toward the NFL baseline

## Phase 6 · Real users and polish
*Jun 1 – Aug 15, 2027*

- [ ] Terms of use and privacy page
- [ ] Pilot with at least one coach
- [ ] Logging, metrics, and alerting
- [ ] Latency and cost tuning
- [ ] Stretch: pre-snap formation recognition from a single frame

> **Gate:** case study published

---

## Not in v1

Play drawing, practice planning, and video or film analysis. Ideas for later go in [`LATER.md`](../LATER.md).
