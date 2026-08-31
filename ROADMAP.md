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

- [x] Handle secured: **@CardVaultSOL** on X and Telegram
- [x] Links written into `vault.json` → footer populates automatically
- [x] Both accounts registered
- [x] X bio and pinned post set
- [x] Telegram description and pinned message set
- [x] Trademark sanity check done — **decision: keep the name, do not pursue registration**
- [x] Original brand assets created — see [brand/](brand/)
- [x] First-acquisition deadline set: **2026-10-30**
- [x] Fee split set: **70 Vault / 30 Operations**
- [x] Season 1 category set: **One Piece Card Game**
- [x] Season 1 target set: **Boa Hancock — Manga Rare, PSA 10, ~€3,500**
- [x] Price estimate confirmed at €3,500 — checked, with deliberate headroom
- [x] Pump.fun fee model verified against official documentation (see README §3)
- [x] Set reference confirmed: **OP07-051**
- [x] Denomination decided: **SOL** — native Pump.fun convention, deepest routing, and volume is the only thing that funds the Vault
- [ ] Prepare the launch post — apply [README §10 language discipline](README.md#10--language-discipline)

### Naming finding

"Card Vault" is a crowded descriptive term in the collectibles space: several
collection-tracker apps of that name on iOS and Android, plus a UK trading-card
retailer trading as The Card Vault. No party holds strong exclusive rights,
so conflict risk is low — but registration is correspondingly hard and not
worth pursuing at this budget.

The real cost is discoverability, not legal exposure. The `@CardVaultSOL`
handle disambiguates well. Distinctiveness has to come from the visual
identity, not the name.

### Competitive landscape

The space has established players, and both use mechanisms this project
deliberately rejected:

* **Collector Crypt (CARDS)** — Solana, tokenises physical cards into
  *redeemable* NFTs with a gacha mechanic. Over $50M cumulative protocol
  revenue by June 2026.
* **Collector Vault** — live breaks, fractional ownership, and a token
  described as *treasury-backed* with cards providing *tangible backing*.

Read this two ways. The thesis is validated: someone is making real money
from crypto plus trading cards. But Card Vault will compete against projects
that are willing to promise redemption and backing, which it will not.
Verifiability is the differentiator, and it has to be executed well enough
to be worth more than a promise.


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

- [ ] Shortlist One Piece Card Game cards within the **actual** budget, not the target budget
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

## Decisions

| # | Decision | Status |
|---|---|---|
| 1 | First-acquisition deadline | ✅ `2026-10-30` (60 days) |
| 2 | Fee split Vault / Operations | ✅ 70 / 30 |
| 3 | Season 1 category | ✅ One Piece Card Game |
| 4 | Season 1 target | ✅ Boa Hancock Manga Rare, PSA 10, ~€3,500 |
| 5 | Set reference + price estimate | ✅ `OP07-051`, ~€3,500 |
| 5b | Pair denomination | ✅ SOL |
| 6 | Brand assets | ✅ Built — see [brand/](brand/) |
| 7 | Custody arrangement | ⬜ Deferred to Phase 5 |
| 8 | Handles + trademark | ✅ @CardVaultSOL secured; name kept, no registration |

---

## Never

* Wash trading or manufactured volume
* Promising the cards back the token
* Announcing a giveaway before the legal structure exists
* Selling Vault cards for anything other than more Vault cards
* Editing history in `vault.json` instead of appending corrections
* **Reproducing official card artwork** — name a target card in text, never publish its art. Photographs of a card the Vault physically owns are a separate matter; publisher artwork and logos are not ours to republish.
