---
name: research-log
description: >-
  Log design research into structured, evidence-first records — interviews, prototype tests,
  critiques, solo prototyping (exploration), and data analyses — and report where a study
  stands as facts, never verdicts. Use when a designer wants to log a research session, process
  interview notes or a transcript, record a prototype test, capture what they decided while
  prototyping, log a design or stakeholder critique, log a decision and what it closes, start a
  new study, or ask where a study stands. Trigger phrases: "log this interview", "log this
  session", "process these notes", "I just tested the prototype with…", "log a crit",
  "I've been prototyping…", "we decided…", "where does [study] stand", "start a study",
  "what do we know about…". Do NOT trigger on passing mentions of research in conversation.
---

# Research Log

Turn whatever the designer has (messy notes, a transcript, a prototype, a data pull) into
structured research records in one pass, with one confirmation. The designer talks; this skill
structures, tags, counts and files.

**Read `reference/rules.md` before the first write in a conversation.** It holds the rules
this workflow applies: the five kinds of learning, the insight format, the counting rule,
claims, and decisions.

## The one principle

**Surface facts and gaps. Never judge.** Do not say a study is ready, done, strong, weak,
sufficient or insufficient. Do not rank studies. Do not recommend who to talk to next. Do not
mark an insight `addressed` on your own judgment. Only a logged decision does that. Judgment
belongs to the designer, and the records exist to inform it.

## Where files live

On first use in a conversation, find the research root:
1. A `research/` folder in the working directory, or one the designer names.
2. Otherwise propose `research/` in the working directory and create it on the designer's yes.
3. No file access (plain chat): produce each file's content as markdown blocks for the designer
   to save, with the exact filename and path at the top of each.

One folder per study: `research/[study-slug]/`. Layout and templates: `reference/rules.md` →
Files, and `templates/`. Create files and folders **on first use only**. Never scaffold empty
ones, because a missing `sessions/` folder correctly means no sessions yet.

## Modes

Infer the mode from what the designer says. Ask only if it's genuinely ambiguous, and then
inside the confirm block rather than as a separate question.

| Designer says | Mode |
|---|---|
| Notes / transcript of talking with or watching users | **Log** → `generative` |
| A user worked through a prototype | **Log** → `prototype-test` |
| Review, crit, demo, shareout, stakeholder feedback on an artifact | **Log** → `critique` |
| "I've been prototyping…", their own design work, unshared | **Log** → `exploration` |
| Analytics, a query, a UI or content audit | **Log** → `analysis` |
| "We decided…", "we're going with…" | **Decide** |
| "Where does X stand", "what do we know about…" | **Status** |
| "Start a study on…" | **Start** |

---

## Log

### Phase A — Read and draft silently (write nothing yet)

1. **Find the study.** Match it to an existing `research/[slug]/`. If there's no match, draft a new
   study (Start mode) inside the same confirm block.
2. **Read what's on file** for that study: `Research-Log.md` (insights, questions,
   contradictions), `Claims.md`, `Decisions.md`, and `Brief.md` if one exists.
3. **Extract observations** using the template for the mode (`templates/`). Each observation
   must make sense without the source:
   - quote the full spoken passage (2–5 sentences), with a timestamp when the source has one
   - define field terms a later reader wouldn't know, in a `## Field terms` section
   - log slips of the tongue as heard, with a `note:` line. Never silently correct them.
   - ignore logistics, crosstalk and filler
4. **Tag every observation:** `speaker`, `prompt` (unprompted · prompted · leading), `method`
   (observed · stated · reacted), and `theme` (reuse existing themes in the log before inventing
   one; mark a new one `new?`).
5. **Hold interpretations.** Anything with evaluative language ("this means", "suggests",
   "clearly", "therefore", "the problem is") goes to `## Held — possible interpretations`,
   not into an observation. Never discard held items; surface them.
6. **Build insights.** One atomic insight per observation worth keeping (format in
   `reference/rules.md`), destined for `Research-Log.md` → `## Insights`, newest first.
7. **Check against what's on file:**
   - **Claims:** does any observation count for or against an existing claim? Draft new
     For/Against counts using the counting rule. Flag **counter-evidence on a `held` claim**.
     Propose a new claim only where the observation would change a design decision.
   - **Contradictions:** an observation that conflicts with a prior insight or a held claim
     becomes a proposed contested pair.
   - **Questions:** mark questions this speaks to as `partial?` or `answered by evidence?`.
     Route new ones to Open, Design, or Engineering & Data questions.
   - **Exploration:** draft the question explored, decisions with reasons, bets created
     (each a proposed `bet · emerging` claim, For 0 · Against 0), alternatives dropped, and
     what's still open. Source this from what the designer says and from the prototype itself if
     readable (code comments, annotations).
8. **Draft the change note** for `Research-Log.md` → `## Change notes` (format in
   `reference/rules.md`). Facts only.

### Phase B — One confirmation, exceptions only

Apply everything drafted with confidence. Show only what needs the designer's eye:

```
LOG: [title] — YYYY-MM-DD — [mode] · voice: [voice] → research/[slug]/sessions/[file]
  [N] observations · [N] insights · [N] claim links · change note ready

CHECK THESE ([N]):
1. Tag? — OBS 7 prompt: leading? (interviewer suggested it, participant said "yeah")
2. New theme? — `trust-signals` (close to: `credibility`)
3. Counter-evidence on held claim — C-04 "Users compare plans side by side" ← OBS 3, OBS 9
4. Proposed new claim — "Users read the total before the line items" (belief, emerging)
5. Held as interpretation? — "they don't trust the estimate"

Apply, or correct by number?
```

Mark low-confidence inferences with `?`. If nothing needs checking, show the header line plus
`Apply?`. Never print every observation in the block, because the full extraction goes into the
file. Never ask a question before this block; draft through any gaps with `[unknown]`.

### Phase C — Write (after the yes)

Session file → insights → claim counts and history lines → contested pairs → question
updates → `## Sessions` row → change note. **Never change a claim's state** (emerging → held,
etc.). Propose it with a trailing `?`. The designer sets states.

Close with three lines max:
```
Logged: [title] — [N] insights · [N] claim links · [N] questions touched
→ research/[slug]/Research-Log.md
```

---

## Decide

1. Draft a `Decisions.md` row: date, decision, rationale, made by, closes, supersedes. Create
   the file from `templates/decisions.md` on first decision.
2. List the study's open questions and open insights, numbered, and ask **once**: *"Does this
   close any of these? (numbers / n)"*. `n` is a fine answer, and the decision is logged either way.
3. For each one named:
   - question → `- [x] **RESOLVED YYYY-MM-DD by decision:** [decision] — [original question]`
   - insight → `status: addressed` + `addressed_by: [decision date + short name]`
   - bet or belief it settles or overrides → a dated `## History` line on the claim with the
     reasoning; propose the state change with `?`
4. If the decision goes against the research, record that explicitly with the reasoning. Never
   delete or soften the earlier evidence.

---

## Status

Computed fresh from files every time. Nothing here is stored.

```
STATUS: [Study] — YYYY-MM-DD

LOGGED:
→ [N] sessions · [N] people · [N] groups (user) · critique: [N] · data: [N] · explorations: [N]
→ Last logged: YYYY-MM-DD ([N]d ago) — [title]

CLAIMS:
→ Untested bets: [N] — C-xx [short], C-yy [short]
→ Contested: C-xx ⟷ C-yy ([N]d open) — settle by: [line]
→ Nothing against: [N] claims
→ Proposed states awaiting you: [N]

QUESTIONS:
→ Open: [N] · Design: [N] · Engineering & Data: [N] · Resolved by decision: [N]

COVERAGE:
→ Reached: [groups] · Named in brief, not reached: [groups]

DATED JUDGMENTS:
→ "[any readiness/confidence statement found]" — written YYYY-MM-DD ([N]d ago)
```

Omit empty sections. An undated judgment found in a file displays as `(undated — treat as
stale)`. Never rewrite it unless asked. **Never add a line that interprets these numbers.**

---

## Start

Draft `research/[slug]/` with `Research-Log.md` from the template. Offer, without blocking, to
draft a `Brief.md` (question, who, by when, what it feeds) and to seed `Claims.md` with the
designer's current beliefs and bets. If they decline, nothing else is created. A study without a
brief is exploratory, which is a valid state and not an error.

---

## Never

- Say ready / not ready, enough / not enough, strong / weak; give a confidence score
- Write an undated verdict into any file
- Mark an insight `addressed` without a logged decision
- Change a claim's state (propose with `?` only)
- Count observations instead of sessions · people · groups
- Count critique, data or exploration as user evidence
- Paraphrase and call it evidence (label it `[paraphrased — no direct quote]`)
- Overwrite existing content. Append, or prepend where newest-first applies.
- Quote material marked `visibility: private` anywhere except its own session file
- Interrupt with sequential questions (one batched confirm per pass)
