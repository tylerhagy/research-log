# Rules

The skill applies these rules. Read them before the first write in a conversation.

---

## Five kinds of learning

Every evidence file carries `mode:`. The mode decides the template, what the record produces,
and how it counts.

| Mode | Template | Produces | Counts as |
|---|---|---|---|
| `generative` | `session.md` | Observations about what people do and need | Sessions, when `voice: user`; otherwise `critique: N` |
| `prototype-test` | `test.md` | Observed behavior against named bets | Sessions, for the bets it tests |
| `critique` | `critique.md` | Points raised on an artifact | `critique: N` only. Never user evidence. |
| `exploration` | `exploration.md` | Decisions, bets (`bet · emerging`), alternatives dropped | Never counted. It creates bets, not evidence. |
| `analysis` | `analysis.md` | Measured facts with provenance | `data: N` |

File names: `YYYY-MM-DD-[slug]-[session|test|critique|exploration|analysis].md` in `sessions/`.

**Voice** (`voice:` in frontmatter): whose evidence this is.
- `user`: people who would use the product. Only `user` counts as user evidence.
- `stakeholder`: leadership, SMEs, developers, internal experts, even very knowledgeable ones.
- `self`: the designer's own statements, audits or prototypes. Never counted.
- `data`: analytics and queries.

**Fidelity** (`fidelity:`): how the record was produced.
- `firsthand`: the designer was present, or validated a verbatim transcript.
- `secondhand`: someone else's notes or summary.
- `reconstructed`: rebuilt from memory or partial records. Say so in the body too.

---

## Atomic insight

One insight per block, fields on separate lines, newest first, blank line between blocks.

```
observation: [one sentence — what happened or was said]
evidence: [verbatim quote or specific observed behavior]
user_type: [role / segment, or [unknown]]
theme: [one tag]
session: [[YYYY-MM-DD-slug-mode]]
prompt: unprompted | prompted | leading
method: observed | stated | reacted
voice: user | stakeholder | self | data
status: open | addressed | invalidated
addressed_by: [decision — only when status is addressed]
invalidated_by: [session — only when status is invalidated]
visibility: private            ← only when private
```

- `observation` and `evidence` are required; everything else may be `[unknown]`.
- `status` defaults to `open` when absent.
- `evidence` is verbatim or a specific behavior. Otherwise write `[paraphrased — no direct quote]`.
- Never combine two observations in one block.

**Prompt tags** matter more than they look:
- `unprompted`: they raised it themselves.
- `prompted`: they answered a neutral question.
- `leading`: the interviewer proposed it and the participant agreed ("Yeah", "Right").
  A `leading` observation is still logged. It just isn't the same strength as an unprompted one.

**Method tags:** `observed` (they did it) · `stated` (they said it) · `reacted` (response to
something on screen). Observed behavior outranks stated preference.

---

## Observation vs. interpretation

- OBSERVATION: "Dana scrolled past the summary twice before finding the total." ✓
- INTERPRETATION: "The summary is too long." ✗ → hold it

Watch for evaluative language: *this means, suggests, implies, therefore, clearly, the
problem is, they don't trust, they want*. Move it to `## Held — possible interpretations` and
ask the designer in the confirm block. Never discard it.

---

## Counting evidence

Count **distinct sessions · distinct people · distinct user groups. Never observations.**
Five observations from one person in one session = 1 session · 1 person · 1 group.

Counted separately and never added to user evidence: `critique: N`, `data: N`. Exploration is
never counted.

Say so when every supporting group is non-user: `For: 2 sessions · 3 people · 0 users`.

`secondhand` evidence is reported as such: `1 session (secondhand)`.

Reporting a count is a fact. Calling it enough, too few, strong or weak is a verdict, and is never
written or said.

---

## Claims — `Claims.md`

One ledger per study. Two types:
- `belief`: what we think is true about users or the world. Comes from research.
- `bet`: what the design assumes. Comes from exploration and prototypes.

**Only claims that would change a design decision if wrong.** Aim for 15–30. Everything else
stays an insight. Propose new claims in the confirm block and never create one silently.

**States:** `emerging → held → contested → revised | retired`. Claims can move back and forth.
- Only the designer changes a state. The skill proposes with a trailing `?` (`held?`).
- Never overwrite. Every change appends a dated line under `## History`. A wording change keeps
  the old wording.

**Against is required.** An empty Against cell is written `0`, never blank.

**Untested bet:** a `bet` that is still `emerging` with no session evidence For or Against.
Critique and data alone don't count as a test.

**Contested pairs:** two conflicting claims linked `C-xx ⟷ C-yy` under `## Contested pairs`,
each keeping its own counts, plus a **what would settle it** line. Nothing forces a winner.
When resolved, record how in both histories:
`one-wins` · `both-true-by-group` · `both-true-by-context` · `reframed` · `still-open (reviewed YYYY-MM-DD)`.

IDs are `C-01`, `C-02`… per ledger and are never reused.

---

## Decisions close questions

A decision is an input to research as well as an output. It is the **only** thing that moves an
insight to `addressed`.

`Decisions.md` columns: Date · Decision · Rationale · Made by · Closes · Supersedes.
- **Closes** names the questions or insights resolved. Free text is fine.
- **Supersedes** names any earlier decision or research lean this overrides.

A decision may go against the research. That's legitimate. Record the reversal and its
reasoning, and keep the earlier evidence, because it is usually what makes the reversal
defensible later.

---

## Verdicts are never stored

- Never write an undated readiness or confidence statement ("ready to design", "confidence:
  medium").
- Any judgment the designer writes carries its date, and status views show its age.
- An undated one found in a file is shown as `(undated — treat as stale)`. It is never rewritten
  without being asked.

---

## Where questions live

The test is: **will I run into this naturally when I do the work, or will it rot sitting here?**

Most questions raised in research are design sub-decisions that you'll hit anyway when you design
that piece. They stay in the study log:

| Section | Holds | Answered by |
|---|---|---|
| `## Open questions` | Research questions | A session, study or analytics |
| `## Design questions` | Design sub-decisions | Sketching and prototyping |
| `## Engineering & data questions` | Technical unknowns | A query or engineering investigation |

A question leaves the log only when (a) **someone else has to act**, in which case it goes on their
agenda and stays listed here too, or (b) **it has a deadline and a real consequence**, in which case
it goes on the designer's task list. Most questions don't qualify.

Question format: `- [question] — added: YYYY-MM-DD`. Resolved:
`- [x] **RESOLVED YYYY-MM-DD by decision:** [decision] — [question]`.

---

## Change notes

One per logged record, in `Research-Log.md` → `## Change notes`, newest first:

```
### YYYY-MM-DD — [title] → [[file]]
- Added: [N] observations · [N] insights · voice: [voice] · mode: [mode]
- Claims: C-03 +1 session for · C-05 counter-evidence · new C-09? (emerging)
- Contested: [new pair, or "none"]
- Questions: [answered / partial / new, by short name]
- Coverage: [groups reached] · still not reached: [groups]
```

Facts only. No "this suggests".

---

## Private material

`visibility: private` on a session or a single observation. Status views **count** private items
and say they exist, and **never quote** them. **Critical remarks about named people** stay in the
session file only, whether or not they're marked.

---

## Files

```
research/[study-slug]/
├── Brief.md            optional — its absence makes the study exploratory
├── Research-Log.md     sessions index · insights · questions · contradictions · change notes
├── Claims.md           created when the designer seeds it or accepts a first proposed claim
├── Decisions.md        created on first decision
└── sessions/           every dated evidence file, created on first session
```

Naming: study folders are lowercase-hyphenated. Dated files start with `YYYY-MM-DD`. Use
filename wikilinks (`[[2026-03-04-checkout-dana-session]]`), not path links, so they survive
moves.
