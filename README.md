# research-log

A Claude skill for designers who run their own research. You give it notes, a transcript, a prototype or a data pull. It writes structured records: observations with verbatim evidence, atomic insights, a ledger of what you believe and what you are betting on, and a log of decisions.

It reports facts and gaps and does not judge them. It never tells you that you are "ready to design", never scores your confidence, and never marks a question answered unless a decision answered it. The judgment stays with you.

Works in Claude Code, Cowork and Claude Desktop.

---

## Why it works this way

Each rule exists because skipping it caused a real problem. You don't need to adopt all of them on day one, but each one prevents a specific failure.

**Observations and interpretations are kept apart.**
"She said she never reads the notes" is an observation. "The notes feature is broken" is an interpretation. Mix them during logging and three weeks later you can't tell what someone said from what you assumed. The skill holds anything that reads like interpretation ("this suggests", "clearly", "which means") and asks you about it.

**Evidence is verbatim or labeled as not.**
A paraphrase is already an interpretation. If there is no direct quote, the record says `[paraphrased]`.

**Evidence is counted by sessions, people and groups, never by observations.**
Twelve observations from one enthusiastic person in one session count as one session, one person and one group. Counting observations makes a single talkative participant look like a pattern.

**There are five kinds of learning, and only some of them are user evidence.**

| Kind | Example | Counts as user evidence? |
|---|---|---|
| `generative` | Interview, observation, field visit | Yes, when the voice is a user |
| `prototype-test` | A real user works through your prototype | Yes, for the bets it tests |
| `critique` | Design crit, stakeholder review, leadership demo | No. Counted separately as `critique: N` |
| `exploration` | You prototyping alone | Never. It creates bets, not evidence |
| `analysis` | Analytics, data query, UI audit | Counted separately as `data: N` |

A VP liking your prototype is useful, but it isn't evidence that users can complete the task. Keeping these counts separate stops stakeholder agreement from turning into "validated".

**Solo prototyping gets logged too.**
Every prototype makes assumptions, such as "users will scan this as a timeline" or "nobody needs bulk edit". If you don't write them down when you make them, they become invisible facts in the code. An exploration record turns each one into a named bet you can test later.

**Beliefs and bets share one ledger, and "Against" is never blank.**
`Claims.md` holds the 15–30 claims that would change a design decision if they turned out wrong. Each one has For and Against counts. An empty Against is written `0` so you can see which claims have never been challenged.

**Contradictions stay on the record.**
When two claims conflict, they are linked as a contested pair with a line saying what evidence would settle it. Nothing forces a winner, and the newest session doesn't automatically win.

**Only a decision closes a question.**
Research narrows a question, and a decision closes it. Decisions are logged with the questions they close and anything they supersede. If a decision goes against the research, the reversal is recorded with its reasoning and the earlier evidence stays. That earlier evidence is usually what makes the reversal defensible later.

**Verdicts are never stored.**
An undated "confidence: high" written in August is still read as current in November. Anything that sounds like a judgment carries a date and is shown with its age. Status views report counts and gaps, never "enough" or "strong".

**Questions stay where you'll run into them.**
Most questions that come up in research are design sub-decisions, such as "should the icons have labels?". You'll face them anyway when you design that screen, so they don't belong on a to-do list. They stay in the study log under Open, Design or Engineering & Data questions. A question leaves the log only when someone else has to act on it, or when it has a deadline and a real consequence.

---

## Install

**Claude Code**
```
/plugin marketplace add tylerhagy/research-log
/plugin install research-log@research-log
```

**Claude Desktop / Cowork**
Download `plugins/research-log/skills/research-log/` as a zip and upload it under Settings → Capabilities → Skills.

---

## Using it

Talk to it normally:

- *"Log this interview"* + notes or a transcript
- *"Log a prototype test, Dana tried v3 of the checkout"*
- *"I've been prototyping the filters, log what I decided"* (exploration)
- *"We decided to drop bulk edit"* (decision; it asks which questions this closes)
- *"Where does the checkout study stand?"* (status: facts only)
- *"Start a new study on onboarding"*

Each logging pass ends with **one** confirmation that lists only what needs your eye: uncertain tags, held interpretations, counter-evidence on a claim you hold, and proposed new claims. Everything else is written as drafted.

---

## What it creates

```
research/
└── [study-slug]/
    ├── Brief.md            optional: the question, who, by when
    ├── Research-Log.md     sessions, insights, questions, contradictions, change notes
    ├── Claims.md           beliefs and bets, with For / Against counts
    ├── Decisions.md        what was decided, why, and which questions it closed
    └── sessions/
        ├── 2026-03-04-checkout-dana-session.md
        ├── 2026-03-06-checkout-v3-test.md
        ├── 2026-03-07-checkout-crit-critique.md
        ├── 2026-03-02-checkout-filters-exploration.md
        └── 2026-03-09-checkout-dropoff-analysis.md
```

All files are plain markdown and work in Obsidian, VS Code or any folder. See `examples/` for a complete fictional study.

---

## Origin

This started as part of a personal Obsidian and Claude Code system for running research alongside a design lead's job. Everything specific to that setup has been removed.

## License

MIT
