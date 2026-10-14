# Grocery Checkout — Research Log

*Brief: [[Brief]]*

## Sessions

| Date | Mode | Voice | Participants | User type | File |
|---|---|---|---|---|---|
| 2026-03-07 | critique | stakeholder | Head of Operations, 2 designers | — | [[2026-03-07-checkout-v3-critique]] |
| 2026-03-06 | prototype-test | user | Marcus | occasional top-up shopper | [[2026-03-06-checkout-v3-test]] |
| 2026-03-04 | generative | user | Dana | weekly family shopper | [[2026-03-04-checkout-dana-session]] |
| 2026-03-02 | exploration | self | — | — | [[2026-03-02-checkout-v2-exploration]] |

## Insights

observation: Marcus tried to change a quantity on the checkout screen and couldn't.
evidence: Tapped the item row twice. "Can I not just make it two here? I have to go back?"
user_type: occasional top-up shopper
theme: checkout-editing
session: [[2026-03-06-checkout-v3-test]]
prompt: unprompted
method: observed
voice: user
status: addressed
addressed_by: 2026-03-10 — Allow quantity edits at checkout

observation: Marcus went to the total first, then expanded the items.
evidence: Hovered the total, then clicked "Show 9 items". "OK, thirty-two, what's in there."
user_type: occasional top-up shopper
theme: expected-total
session: [[2026-03-06-checkout-v3-test]]
prompt: unprompted
method: observed
voice: user
status: open

observation: Dana compares the checkout total to a number she already expects.
evidence: "I know it's going to be about one-forty. If it says one-ninety I know something's wrong and I go hunting."
user_type: weekly family shopper
theme: expected-total
session: [[2026-03-04-checkout-dana-session]]
prompt: unprompted
method: stated
voice: user
status: open

## Open questions
- [x] **RESOLVED 2026-03-10 by decision:** Allow quantity edits at checkout, locked once picking starts — Do shoppers try to edit at checkout? — added: 2026-03-02
- Do top-up shoppers carry an expected total the way weekly shoppers do? — added: 2026-03-04

## Design questions
- Where do promo codes go in a total-first layout? — added: 2026-03-02

## Engineering & data questions
- What is the current substitution error rate for orders edited after placement? — added: 2026-03-07

## Change notes

### 2026-03-07 — v3 crit → [[2026-03-07-checkout-v3-critique]]
- Added: 1 point · 0 insights · voice: stakeholder · mode: critique
- Claims: C-02 critique: 1 against
- Contested: none
- Questions: new — late-edit error rate (engineering & data)
- Coverage: unchanged

### 2026-03-06 — v3 test, Marcus → [[2026-03-06-checkout-v3-test]]
- Added: 2 observations · 2 insights · voice: user · mode: prototype-test
- Claims: C-01 +1 session for · C-02 +1 session against · C-02 retired? (proposed)
- Contested: none
- Questions: partial — "Do shoppers try to edit at checkout?"
- Coverage: occasional top-up shoppers reached · weekly family shoppers not yet tested

### 2026-03-04 — Dana interview → [[2026-03-04-checkout-dana-session]]
- Added: 2 observations · 1 insight · voice: user · mode: generative
- Claims: new C-03 (belief, emerging) +1 session for
- Contested: none
- Questions: new — top-up shoppers' expected total
- Coverage: weekly family shoppers reached · occasional top-up shoppers not reached

### 2026-03-02 — v2 exploration → [[2026-03-02-checkout-v2-exploration]]
- Added: 2 bets (C-01, C-02) · voice: self · mode: exploration
- Questions: new — edits at checkout; promo code placement
