# Claims — Grocery Checkout

*Beliefs (from research) and bets (from design). Counts are sessions · people · groups, never observations; critique and data are counted separately. Only the designer changes a state; a trailing "?" means proposed.*

## Ledger

| ID | Type | Claim | State | For | Against | What would settle it | Last touched |
|---|---|---|---|---|---|---|---|
| C-01 | bet | Shoppers look for the total before the line items | emerging | 1 session · 1 person · 1 group | 0 | Weekly shoppers in a test | 2026-03-06 |
| C-02 | bet | Nobody needs to change quantities at checkout | retired | 0 | 1 session · 1 person · 1 group · critique: 1 | — | 2026-03-10 |
| C-03 | belief | Shoppers compare the total to an amount they already expect | emerging | 1 session · 1 person · 1 group | 0 | Top-up shoppers; a test where the total is off | 2026-03-04 |

## Contested pairs

*None yet.*

## History

### C-01 — Total before line items
- 2026-03-02 — created as bet from exploration — [[2026-03-02-checkout-v2-exploration]]
- 2026-03-06 — +1 session for (observed) — [[2026-03-06-checkout-v3-test]]

### C-02 — No quantity changes at checkout
- 2026-03-02 — created as bet from exploration — [[2026-03-02-checkout-v2-exploration]]
- 2026-03-06 — +1 session against (observed, failed task) — [[2026-03-06-checkout-v3-test]]
- 2026-03-07 — critique: 1 (operations cost of late edits; bears on how, not whether) — [[2026-03-07-checkout-v3-critique]]
- 2026-03-10 — retired by decision "Allow quantity edits at checkout, capped before pick start" — [[Decisions]]

### C-03 — Expected-total comparison
- 2026-03-04 — created as belief, +1 session for — [[2026-03-04-checkout-dana-session]]
