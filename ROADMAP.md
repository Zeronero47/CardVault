# 🗺️ Roadmap

Executable steps in order. Each phase has an exit condition — do not start the next one until it is met.

---

## ✅ Phase 0 — Repository & site (today)

- [x] Consolidate naming: **Card Vault** / `$VAULT` / repo `CardVault`
- [x] Rewrite README against locked design decisions
- [x] Treasury architecture documented ([TREASURY.md](TREASURY.md))
- [x] `vault.json` schema and empty initial state
- [x] Static site (`index.html`) reading `vault.json`, no hardcoded figures
- [ ] **Enable GitHub Pages** — Settings → Pages → Source: `main`, folder `/ (root)`
- [ ] **Push to `main`**
- [ ] Verify live at `https://zeronero47.github.io/CardVault/`

**Exit condition:** the site is publicly reachable and shows the empty Vault honestly.

---

## Phase 1 — Pre-launch preparation

Nothing here costs money. Do not launch the token until all of it is done.

- [ ] Check handle availability: X, Telegram, and optionally a domain
- [ ] Create X account, set bio and pinned post with the disclaimer
- [ ] Create Telegram channel
- [ ] Add real links to `vault.json` → `links` (site picks them up automatically)
- [ ] Trademark sanity check on "Card Vault"
- [ ] Commission or create **original** artwork — no official card art, no rights-holder logos
- [ ] Confirm the first-acquisition deadline (currently `2026-11-29`)
- [ ] Confirm the fee split (currently 50 / 50)
- [ ] Re-verify current Pump.fun creator fee mechanics and fee-sharing setup
- [ ] Prepare the launch post — apply [README §10 language discipline](README.md#10--language-discipline)

**Exit condition:** brand, channels and disclaimers are live and consistent; artwork exists.

---

## Phase 2 — Launch

- [ ] Create VAULT and OPERATIONS wallets
- [ ] Set up the Squads multisig for VAULT
- [ ] Launch `$VAULT` on Pump.fun
- [ ] Configure Creator Fee Sharing with the confirmed split
- [ ] Fill `vault.json`: `token.contract`, `token.launchedAt`, both wallet addresses
- [ ] Commit and push — the site flips from `PRE-LAUNCH` to `LIVE` on its own
- [ ] Publish contract address across all channels simultaneously

**Do not promise a giveaway. Do not imply the cards back the token.**

**Exit condition:** the token is live and the contract address is public everywhere.

---

## Phase 3 — Validation (7 days)

- [ ] Track daily: volume, holders, unique traders, creator fees
- [ ] Claim fees and record each claim in `vault.json` with its transaction hash
- [ ] Post daily — the empty Vault and the running countdown are the content
- [ ] Day 7: decide

> **If there is no organic volume, stop.** Do not launch another token to manufacture activity. A clean shutdown preserves the ability to try something else later; a pump-and-dump does not.

**Exit condition:** a documented go / no-go decision.

---

## Phase 4 — First acquisition (by the committed deadline)

- [ ] Choose the category, then the specific card, within the actual budget
- [ ] Community vote on the shortlist
- [ ] Purchase — prefer an already-graded card so the certificate is immediately verifiable
- [ ] Record in `vault.json`: transaction hash, SOL, EUR rate, price, grader, certificate number, receipt
- [ ] Commit and push — slot `#001` fills automatically
- [ ] Publish the reveal: unboxing, certificate lookup, full cost breakdown

**If the Vault is empty on the deadline, say so publicly.** The commitment is to the date and to the honesty, not to a guaranteed purchase.

**Exit condition:** slot `#001` is filled and independently verifiable, or the shortfall is publicly documented.

---

## Phase 5 — Community

- [ ] Establish the recurring voting mechanism for the next target
- [ ] Publish the digital catalogue
- [ ] Set the next acquisition deadline
- [ ] Decide custody: insured storage or a third-party vaulting service

**Exit condition:** the loop has run twice without special effort.

---

## Phase 6 — Only with real revenue

Not before. Each item requires professional review.

- [ ] Merit-based creative contest (art. 6 lett. a DPR 430/2001 exclusion)
- [ ] Evaluate an entity to hold the collection — removes the operator's ability to liquidate, grants holders nothing
- [ ] Legal review before any prize mechanism is announced
- [ ] Season 2 category

---

## Decisions still open

| # | Decision | Current placeholder |
|---|---|---|
| 1 | First-acquisition deadline | `2026-11-29` (90 days) — change in `vault.json` |
| 2 | Fee split Vault / Operations | 50 / 50 |
| 3 | Season 1 category | Chosen at first acquisition, budget-driven |
| 4 | Logo and art direction | Deferred |
| 5 | Custody arrangement | Deferred to Phase 5 |

---

## Never

* Wash trading or manufactured volume
* Promising the cards back the token
* Announcing a giveaway before the legal structure exists
* Selling Vault cards for anything other than more Vault cards
* Editing history in `vault.json` instead of appending corrections
