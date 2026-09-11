# adaptive-mentor

A portable instruction file that turns any coding agent (opencode, Claude Code, or
anything with Read/Write/Bash) into an adaptive Socratic mentor for data science,
Python, and ML — from a true beginner who reads `if`/`for` but can't predict what it
does, to an advanced practitioner auditing their own real work.

No hooks, no scripts, no plugin runtime. It's a single markdown file the agent reads
and follows as a hard rule set. That's a real tradeoff: it costs the mechanical
enforcement a hooked plugin gets for free, in exchange for running anywhere.

## The core idea

**One dial, not a level system for its own sake.** For each knowledge domain
(`python`, `wrangling`, `stats`, `classical_ml`, `deep_learning`, `llm_agents`,
`mlops`, `research_rigor`), the mentor tracks how much of the work is actually yours
— from "I write it, you get questioned" (level 1) to "I write nothing and only ask"
(level 5). Higher level means the mentor does *less* for you, not more — the axis
exists to build capability in a beginner and to fight atrophy/complacency in an
advanced practitioner who's stopped producing from a blank page.

**Fast, baby steps toward one clear big goal.** No disconnected drills. The mentor
co-designs a real project with the learner, lays out the whole staircase of steps up
front, and every session ends in something that actually runs.

**Two goal shapes.** `build` — something that doesn't exist yet, from a first script
to an expert-level new domain. `harden` — something real that already exists and needs
to survive scrutiny (a dissertation chapter, a model going to production): the mentor
switches into an adversarial-reviewer mode to find what a hostile reviewer would
attack, then hands each finding back to be fixed at the learner's real skill level.

**State that doesn't reset every project.** Domain competence, confidence-calibration
history, and spaced-review queues live in `PROFILE.md` next to this skill and follow
the learner across every repo. What's being built right now — the goal, the staircase,
session log — lives in `REPO_STATE.md` in the project itself.

Full mechanism (the ladder, handoff loop, Feynman mode, spaced repetition, root-cause
tracing, confidence calibration, anti-adulation gate on leveling up, antipattern
tracking) is documented in [`skill/SKILL.md`](skill/SKILL.md) — start with **THE
ALGORITHM** section near the top, which is written to be followable even by a
smaller/weaker model.

## Install

**opencode:** a native agent wrapper is included at
[`.opencode/agent/mentor.md`](.opencode/agent/mentor.md) — clone this repo, open
opencode inside it, and switch to the `mentor` agent.

**Any other agent (Claude Code, etc.):** point it at the file directly, e.g.:

```
Read skill/SKILL.md in full. From now on you ARE the mentor persona it defines —
follow it exactly, including THE ALGORITHM section. Start with whatever THE
ALGORITHM's first step calls for.
```

## Not tied to data science

Only two things in `SKILL.md` are DS/ML-specific: the domain table (§2) and the
antipatterns table (§9) — everything else (the axis, the ladder, spaced repetition,
goal/staircase protocol) is domain-agnostic. Swap those two tables to repurpose the
mentor for a different field entirely (§2.0 shows a worked example for a
writing/research-mentoring pack).

## Credit

The pedagogical axis — the authorship-level dial, the hint ladder, Feynman mode,
Leitner review — is ported (as plain instructions, no hooks) from
[VicBa2000/socratiskill](https://github.com/VicBa2000/socratiskill) (MIT), a Claude
Code plugin that enforces the same ideas mechanically via hooks. This version trades
that enforcement for portability across any agent.

## License

MIT — see [LICENSE](LICENSE).
