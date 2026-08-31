# 🏦 Treasury & Transparency

How money enters the Vault, how it leaves, and how anyone can check both without trusting us.

---

## The rule

> **No number appears on the site that is not derived from a public address or a public certificate number.**

The website reads [`vault.json`](vault.json) and computes every figure from it. Nothing is typed into the page by hand. If a number cannot be traced to a transaction hash or a grading certificate, it does not get published.

---

## Layer 1 — Split at platform level

Since January 2026 Pump.fun supports **Creator Fee Sharing**: creator fees can be split across multiple wallets with assigned percentages, claimed independently.

```text
Creator Fees
     │
     ├── 50%  →  VAULT wallet       (collectible fund)
     └── 50%  →  OPERATIONS wallet  (costs, reserve)
```

Why this matters: the split is enforced by the platform, not by our word. There is no moment where Vault funds pass through a personal wallet and require anyone to trust that a transfer happened.

**Honest limitation:** percentages are reassignable by the creator after launch. This is transparent, not immutable. The configuration lives in this repository, so any change to it is a public diff.

> ⚠️ Verify current Pump.fun fee mechanics before launch. Platform policies change — this is a named project risk.

---

## Layer 2 — Vault wallet custody

The VAULT is currently a **single-signature wallet**, not a multisig.

**State this plainly rather than implying custody guarantees that do not exist:** one key can move the funds. What the setup does provide is full auditability — anyone can read the balance and every transaction on Solscan without asking us for anything.

### Why not a multisig yet

A Squads multisig was priced during setup at **~0.1028 SOL** to deploy (0.1 SOL one-time platform fee plus rent). With a single operator the only threshold available is 1-of-1, which provides no security benefit over a plain wallet — one key still authorises everything. Paying roughly half of the project's entire declared budget for that, before the Vault holds anything and before demand is validated, contradicts the principle in [README §16](../README.md#14--mvp): validate before spending.

### Migration trigger

Move the Vault to a Squads multisig when **both** are true:

1. The Vault holds enough that ~0.1 SOL is a rounding error rather than half the budget — roughly €200–300
2. There is a genuine second signer, so the threshold can be 2-of-2 or better

A second wallet controlled by the same person is not a second signer. It is security theatre, and presenting it as multisig protection would be misleading.

The migration changes the published Vault address. That is acceptable and will be published as an event with its full transaction trail — a project strengthening custody once it has something to guard is a better story than one that spent its budget on empty infrastructure.

---

## Layer 3 — The off-chain gap

This is where projects like this normally lose credibility: SOL becomes EUR, EUR becomes a card, and the public trail stops.

Every acquisition closes the gap with:

| Evidence | Purpose |
|---|---|
| Outgoing transaction hash | Proves funds left the Vault wallet |
| SOL amount + EUR rate + timestamp | Makes the conversion checkable |
| Purchase receipt (personal data redacted) | Documents the trade |
| **Grading certificate number** | Proves the card exists, independently |

The certificate number is the strongest evidence available. PSA, BGS, CGC and TAG all expose public lookup databases. Anyone can enter the number and confirm the card, its grade and its identity. A receipt screenshot is trivially faked; a certificate entry in a third-party database is not.

---

## Layer 4 — The public ledger

[`vault.json`](vault.json) is committed on every event. Git history provides a timestamped, tamper-evident log at zero cost, already hosted.

### Schema

```jsonc
{
  "meta":   { "updated": "YYYY-MM-DD", "currency": "EUR" },
  "token":  { "ticker": "VAULT", "contract": "<mint address>" },
  "config": {
    "firstAcquisitionDeadline": "2026-11-29",
    "allocation": { "vault": 0.5, "operations": 0.5 },
    "manifestSlots": 8
  },
  "wallets": { "vault": "<address>", "operations": "<address>" },

  "fees": [
    {
      "date": "2026-09-14",
      "tx":   "<solana tx signature>",
      "sol":  1.42,
      "eur":  213.55
    }
  ],

  "acquisitions": [
    {
      "id":       1,
      "date":     "2026-11-29",
      "item":     "Card name",
      "set":      "Set name",
      "grader":   "PSA",
      "cert":     "12345678",
      "certUrl":  "https://www.psacard.com/cert/12345678",
      "priceEur": 180.00,
      "sol":      1.15,
      "tx":       "<solana tx signature>",
      "receipt":  "docs/receipts/001.pdf"
    }
  ]
}
```

`fees[].eur` records what actually landed in the VAULT wallet, already post-split.

**Vault balance** displayed on the site = `sum(fees.eur) − sum(acquisitions.priceEur)`. It is computed, never stored.

---

## Layer 5 — Independent verification

Published so third parties can check without us:

* Solscan links for the VAULT and OPERATIONS wallets
* The Squads dashboard URL
* Grading certificate lookups per card
* This repository, including full commit history

---

## Update procedure

On every fee claim or acquisition:

1. Append the entry to `vault.json` with its transaction hash
2. For acquisitions, add the certificate number and receipt
3. Bump `meta.updated`
4. Commit with a descriptive message (`vault: claim 1.42 SOL` / `vault: acquire #001`)
5. Push — GitHub Pages redeploys and the site reflects it automatically

Never edit a historical entry. Corrections are appended, not rewritten — the git history is part of the evidence.

---

## What this does not do

This architecture makes the Vault **verifiable**. It does not make it **collective property**.

The cards are legally owned by the project operator. Holders have no claim on them. Publishing proof of purchase is a transparency measure, not a transfer of ownership, and nothing here should be read as creating one.

The intended long-term direction is to transfer the collection to an entity whose statute prevents its distribution or sale — which removes the operator's ability to liquidate it, without granting holders any redemption right. That step requires real revenue and professional advice, and has not been taken.
