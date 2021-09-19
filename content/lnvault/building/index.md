---
title: "Building LnVault"
date: 2021-10-12
draft: false
---
LnVault is implemented as a SpigotMC plugin that is compatible with both SpigotMC and PaperMC.
<!--more--> 
TL;DR; Source code is located here --> [Github](https://github.com/LnVault/lnvault-plugin.git)


## Pre-requisites

The following tools are required for compilation

 - [Git](https://git-scm.com/)
 - [OpenJDK 16](https://openjdk.java.net/projects/jdk/16/)
 - [Maven](https://maven.apache.org/what-is-maven.html)


[Netbeans](https://netbeans.apache.org/) is the preferred IDE by the LnVault developers.

## Building

```console
lnvault@home:~$ git clone https://github.com/LnVault/lnvault-plugin.git
lnvault@home:~$ cd lnvault-plugin
lnvault@home:~$ mvn package
```

The finished plugin jar will be located at ./target/lnvault-1.0-SNAPSHOT.jar