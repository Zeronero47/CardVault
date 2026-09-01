# 🚀 Launch sheet

Everything to paste at launch, prepared in advance so nothing gets composed
under time pressure. Every line here already follows
[README §10 language discipline](README.md#10--language-discipline) — do not
improvise replacements on the day.

---

## Pump.fun coin setup

| Field | Value |
|---|---|
| Name | `Card Vault` |
| Ticker | `VAULT` |
| Image | `brand/avatar.png` |
| Website | `https://cardvault.art` |
| X | `https://x.com/CardVaultSOL` |
| Telegram | `https://t.me/CardVaultSOL` |
| Denomination | **SOL** |
| Dev buy | **0** — see below |

### Description

```
Card Vault: creator fees buy real graded trading cards.

Every purchase published with its transaction hash and PSA certificate number. Verify it yourself.

Nobody receives a card. The Vault only grows.

Holding $VAULT is not a claim on anything.
```

### Dev buy: zero, and say so

Pump.fun allows the creator to buy supply at creation. The recommendation is
to buy nothing.

*"The creator holds no $VAULT"* removes the single most common accusation
against a memecoin in one sentence, and it is consistent with a project whose
whole premise is that nobody takes anything out — the operator included.

The cost is having no aligned exposure. But a position you might one day sell
is a liability for this specific project: selling it would end the project's
credibility instantly, and holding it forever adds something to explain for no
benefit.

---

## Immediately after launch, before any promotion

1. Configure **Creator Fee Sharing**: 70% Vault, 30% Operations
2. Verify the split shows correctly in the Pump.fun interface
3. Update `vault.json` → `token.contract`, `token.launchedAt`
4. Commit and push — the site flips from `PRE-LAUNCH` to `LIVE` by itself
5. Only now, post

The token is tradeable from the first block. Any fees generated before the
split is configured land in a single wallet and stay visible on-chain
permanently. Promoting before step 2 puts a hole in the transparency record
on day one. With no promotion, that window carries no volume and the problem
does not exist.

---

## Launch post

Identical text on X and Telegram, both pinned.

```
$VAULT is live.

CA: [CONTRACT ADDRESS]

Creator fees buy graded trading cards. 70% of every fee goes to the Vault wallet, split at platform level — published, on-chain, verifiable.

Holding $VAULT gives you no card, no share, no claim, and no promise about price. The cards do not back the token.

First card bought by 30 October 2026, with whatever the Vault holds.

https://cardvault.art
```

Expect fake tokens using the same name and image within minutes of any
attention. The pinned post is the defence: it is where people return to check
the real address.

---

## Published addresses

```
Vault        9Z13RZfSxKrmNcrnzTdhM19TcYfdNjM8Uj9stdFR83Ep
Operations   GT1GViiJ3FeFYzsqHpt19gLqPi5D9AXNjfMqzuoykeZr
```

The signer key is not published. It is not a treasury wallet.

---

## Do not, on launch day

* Promise a giveaway
* Say or imply the cards back the token
* Talk about price, targets or "early"
* Post the contract address anywhere before the fee split is configured
