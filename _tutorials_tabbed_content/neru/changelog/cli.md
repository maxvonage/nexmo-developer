---
title: CLI
language: 
menu_weight: 2
---

### v0.8.16 - (2022-11-01)

* Added:
    * Added instance removal with `neru instance remove` command.

### v0.8.15 - (2022-10-26)

* Added:
    * Added versions to capabilities. Messages V0.1 and V1 can be used by using `messages-v0.1` or `messages-v1` respectively. `messaging`/`messages` points to v0.1.

### 0.8.14 - (2022-09-23)

* Added:
    * Adding `environment` capabilities support for `neru.yml`. The `configurations` capability has been deprecated.

* Fixed:
    * Assets provider support

### 0.8.13 - (2022-08-25)

* Fixed:
    * Fix for empty instance IDs

### 0.8.12 - (2022-08-17)

* Fixed: 
    * Missing incoming request parameters (e.g. `req.query`).

### 0.8.11 - (2022-08-02)

* Fixed: 
    * Debug API Key issue.