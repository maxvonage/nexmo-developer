---
title: NeRu CLI
description: This documentation describes the NeRu CLI
meta_title: NeRu CLI
---

# NeRu CLI

`neru` is the NeRu command-line interface that is required for managing and deploying your applications from the terminal.

## Installation

### Mac

```
curl -O https://api-eu.vonage.com/v1/neru/i/neru-59e69cd7-neru-cli-install-dist/neru-cli_darwin_amd64/neru
chmod +x ./neru 
sudo mv ./neru /usr/local/bin
```

### Windows

```
curl -O https://api-eu.vonage.com/v1/neru/i/neru-59e69cd7-neru-cli-install-dist/neru-cli_windows_amd64/neru.exe
```

### Linux

```
curl -O https://api-eu.vonage.com/v1/neru/i/neru-59e69cd7-neru-cli-install-dist/neru-cli_linux_amd64/neru
chmod +x ./neru 
sudo mv ./neru /usr/local/bin
```

## Setup Account 

Configure your account using your Vonage API key and secret which can be obtained from the [Dashboard](https://dashboard.nexmo.com)

```
neru configure 
```

The command will ask for your a default region as well as your Vonage API key and secret which you can get from the from the [API Dashboard](https://dashboard.nexmo.com/).



