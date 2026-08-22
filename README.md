# request-payments

A [nuthatch](https://github.com/nightswatchhq/nuthatch) nest: **Request Network payment proxies on Ethereum**.

Reference-tagged ERC-20 payments with fees.

One binary, one config file, no graph-node, no gateway, no query fees.

## What it indexes

**Chain:** `mainnet`. **1 contract**, **1 tables**.

| alias | address |
|---|---|
| `c0` | `0x370de27fdb7d1ff1e1baa7d11c5820a324cf623c` |

## Verified

Indexed blocks **25,711,626 to 25,811,562** and sealed **593 events**. Every table below is generated from the vendored ABIs, and the run above is what this nest actually decoded, not an estimate.

## Run it

```sh
nuthatch init --from https://github.com/nightswatchhq/request-payments
cd request-payments
nuthatch dev --dir . --backfill 50000 --seal-direct
nuthatch sql --dir . "SELECT count(*) FROM \"c0__transfer_with_reference_and_fee\""
```

The endpoint in `nuthatch.toml` is keyless and public, so this file is publishable: a `nuthatch.toml` is pinned into the nest's content address and must never carry a credential. It is enough to follow the tip. A **backfill** wants archive depth it may not have: pass your own with `--rpc`, and check it first with `nuthatch doctor --rpc <url>`.

## Tables

```
c0__transfer_with_reference_and_fee
```
