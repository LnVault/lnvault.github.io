---
title: "Installing & Configuring LnVault"
date: 2021-10-12
draft: false
---

LnVault is installed as a standard SpigotMC/PaperMC plugin.
<!--more--> 
Obtain a copy of the plugin by either [building](../building) or [downloading](/binaries/lnvault-1.0-SNAPSHOT.jar) the latest release.

## Pre-Requisites

A Minecraft 1.16+ server supporting plugins
- [SpigotMC](https://www.spigotmc.org/)
- [PaperMC]([https://papermc.io/)

LnVault integrates with multiple economy plugins using the VaultAPI
- [Vault](https://www.spigotmc.org/resources/vault.34315/)

A plugin that provides an economy LnVault has currently been tested with
- [EssentialsX](https://www.spigotmc.org/resources/essentialsx.9089/)

A plugin that provides permissions LnVault has currently been tested with
- [LuckPerms](https://www.spigotmc.org/resources/luckperms.28140/)

LnVault uses [OpenNode](https://www.opennode.com/) to access the lightning network. You will need to create an account and generate API keys for deposits and withdrawal.

## Installation

Copy the lnvault jar to the plugins folder located in the root of your minecraft server.
You can now start your minecraft server

## Configuration

Configuration is performed using the /lnconfig command

|Config Key|Description|Default Value|
|----------|-----------|-------------|
|deposit.limit|Limits the amounts of Satoshis that can be deposited in a 24 hour period|1000|
|withdrawal.limit|Limits the amounts of Satoshis that can be withdrawn in a 24 hour period|1000|
|vault.exchangerate|Exchange rate from BTC to in game currency. | 1000000 --> 0.01 in game = 1 Satoshi|
|vault.joingreeting|Greeting displayed on player joining the server||
|opennode.deposit.key|OpenNode API key for Deposits||
|opennode.withdraw.key|OpenNode API key for Withdrawals||

For a minimal configuration only the opennode.deposit.key must be set.

```console
/lnconfig set opennode.deposit.key <APIKey>
```

**Caution any user with lnvault.config permission will be able to read the API keys**

## Permissions

The following permissions are supported

|Permission|Description|
|----------|-----------|
|lnvault.deposit|Enables a user to deposit via the lndeposit command|
|lnvault.withdraw|Enables a user to withdraw via the lnwithdraw command|
|lnvault.config|Enables a user to read and write configuration via the lnconfig command|

**Caution any user with lnvault.config permission will be able to read the API keys**