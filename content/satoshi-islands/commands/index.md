---
title: "Commands"
date: 2021-10-09
draft: false
description: "List of Satoshi-Island commands"
---
These commands can be used to deposit sats and create private islands
<!--more-->
## Lightning

### Deposit Satoshis

    /lndeposit SATS

See [LnVault Usage](/lnvault/usage) for a full guide

**CAUTION: This is a proof of concept server and may be taken offline at any time. Any deposited BTC are considered a gift to the LnVault developers.**

### Check balance

    /balance

### Send Satoshis to another player

    /pay USERNAME SATS

## Islands

### Create an Island

    /island create BIOME SIZE

See [Island Types](../islands) for a preview of island sizes and biomes

### Teleport to Spawn

    /visit spawn

### Teleport to your Home Island

    /home

### List all your islands

    /homes

### Teleport to another home islands

    /home ISLAND_ID

The ids of yor islands can be found using the /homes command