---
title: "Installing & Configuring LnVault"
date: 2023-03-25
draft: false
---

LnVault is installed as a standard SpigotMC/PaperMC plugin.
<!--more--> 
Obtain a copy of the plugin by either [building](../building) or [downloading](/binaries/lnvault-1.2-SNAPSHOT.jar) the latest release.

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
|deposit.description|Description of the deposit invoice. {0} will be replaced with the local deposit value|LnVault Deposit ${0}|
|withdrawal.limit|Limits the amounts of Satoshis that can be withdrawn in a 24 hour period|1000|
|withdrawal.description|Description of the deposit invoice. {0} will be replaced with the local deposit value. {1} will be replaced with the withdrawal ID. The description MUST contain a {1} token|LnVault Withdrawal ${0} {1}|
|vault.exchangerate|Exchange rate from BTC to in game currency. | 1000000 --> 0.01 in game = 1 Satoshi|
|vault.joingreeting|Greeting displayed on player joining the server||
|opennode.deposit.key|OpenNode API key for Deposits||
|opennode.withdraw.key|OpenNode API key for Withdrawals||
|opennode.callback.port|TCP Port for the internal web hook server. A server restart is needed after changing this setting||
|opennode.callback.url|Base URL at which the web hook server can be reached||

For a minimal configuration only the opennode.deposit.key must be set.

```console
/lnconfig set opennode.deposit.key <APIKey>
```

**Caution any user with lnvault.config permission will be able to read the API keys**

## Web hook configuration

To improve the detection of completed withdrawals it is advised to configure the internal web hook server. Configure the opennode.callback.port to a port number that is reachable from the internet.

```console
/lnconfig set opennode.callback.port <PortNumber>
```

To complete the web hook configuration you must set the URL at which the web hook server can be reached

```console
/lnconfig set callback.url http://yourserver:portnumber
```

** Remember to set the port number in the URL. **

Now restart the minecraft server to start the web hook server.

During deposits and withdrawals opennode will now make calls to the web hook server to update the status of the deposit/withdrawal.

## Permissions

The following permissions are supported

|Permission|Description|
|----------|-----------|
|lnvault.deposit|Enables a user to deposit via the lndeposit command|
|lnvault.withdraw|Enables a user to withdraw via the lnwithdraw command|
|lnvault.config|Enables a user to read and write configuration via the lnconfig command|

**Caution any user with lnvault.config permission will be able to read the API keys**