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
| Dev buy | **$1 bootstrap** — see below |

### Description

```
Card Vault: creator fees buy real graded trading cards.

Every purchase published with its transaction hash and PSA certificate number. Verify it yourself.

Nobody receives a card. The Vault only grows.

Holding $VAULT is not a claim on anything.
```

### Dev buy: $1, disclosed

The plan was to buy nothing. Pump.fun makes that impossible: a coin created
on the platform stays **offchain** until someone makes the first purchase,
which is what establishes the trading pair and deploys the mint.

So the creator bought $1 to deploy it, and nothing since.

```
Wallet   F8bdPkKLL7cVsEDZJrfmX3G1DvvZ4R8g6vvZWuCDDU3u
Holds    348,899 $VAULT — 0.035% of supply
Reason   Required to bring the coin on-chain
Status   Will never be sold
```

Disclosing this up front costs nothing. Having it discovered on Solscan later
would cost everything, on a project whose only real asset is that its claims
check out.

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

The creator holds 0.035%, bought for $1 because Pump.fun needs a first purchase to deploy a coin. It will never be sold.

First card bought by 30 October 2026, with whatever the Vault holds.

https://cardvault.art
```

Expect fake tokens using the same name and image within minutes of any
attention. The pinned post is the defence: it is where people return to check
the real address.

---

## Published addresses

```
Contract     EBfLiCjv6jbbk4pESF3bwGMe8WkMb9NVv8WjAerJpump
Vault        9Z13RZfSxKrmNcrnzTdhM19TcYfdNjM8Uj9stdFR83Ep   70% of fees
Operations   GT1GViiJ3FeFYzsqHpt19gLqPi5D9AXNjfMqzuoykeZr   30% of fees
Creator      F8bdPkKLL7cVsEDZJrfmX3G1DvvZ4R8g6vvZWuCDDU3u   0.035%, never sold
```

The signer key is not published. It is not a treasury wallet.

---

## Do not, on launch day

* Promise a giveaway
* Say or imply the cards back the token
* Talk about price, targets or "early"
* Post the contract address anywhere before the fee split is configured
