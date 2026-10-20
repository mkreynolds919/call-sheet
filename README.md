# CallSheet

An open-source play-calling assistant for football coaches. A model trained
on NFL play-by-play data ranks play options for the current game situation,
retrieval maps them to plays in the coach's own playbook, and an LLM explains
the recommendation with citations.

**Status:** Phase 0 (data exploration). Nothing is deployed yet.
See the [roadmap](docs/ROADMAP.md) and [build log](log/).

## Design principle

The model decides; the LLM only explains. Every recommendation shows its
evidence: similar historical situations, sample sizes, and uncertainty.

## v1 scope

- **Situational recommender:** given down, distance, field position, score,
  and time, estimate expected EPA for each play family, with evidence and
  uncertainty. (EPA, expected points added, measures how much a play changed
  a team's expected scoring.)
- **Playbook retrieval:** a coach adds their plays; the system maps the
  recommendation to specific plays in their book and explains the choice
  with citations.
- **Sideline logger:** tap in each play and result during a game to build
  self-scout and opponent tendencies over a season.
- **Security and evaluation:** tenant isolation, prompt-injection tests, and
  retrieval and faithfulness evals in CI.

**Not in v1:** play drawing, practice planning, video and film analysis.

## Data

Play-by-play data from [nflverse](https://github.com/nflverse) (CC-BY 4.0);
FTN charting data (CC-BY-SA 4.0).

## License

MIT
