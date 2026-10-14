---
study: grocery-checkout
date: 2026-03-02
mode: exploration
voice: self
artifact: checkout-v2.html
version: v2
---

# Grocery Checkout — Total-first layout — Exploration
# 2026-03-02

## Question this version explored
- Can the order total lead the screen, with line items collapsed below it?

## Artifact
- checkout-v2.html — total and delivery window at top, items collapsed; does not show promo codes

## Decisions made
- Total sits above the fold: it's the number people are deciding on
- Line items collapsed by default: the list is already reviewed in the cart

## Bets created
- NEW → C-01 Shoppers look for the total before the line items
- NEW → C-02 Nobody needs to change quantities at checkout

## Alternatives tried and dropped
- Itemized receipt layout: dropped because the total landed below the fold on mobile

## Still open
- Where promo codes go
