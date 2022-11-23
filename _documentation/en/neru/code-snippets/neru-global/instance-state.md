---
title: Get Global State
description: How to get global state
navigation_weight: 1
---

# Get Global State

The `neru` object on the SDK allows you to access global state. Global state uses your instance's [global session](http://localhost:3000/neru/code-snippets/neru-global/get-sessions/javascript#global-session) to persist state as long as your instance is not removed, compared to the [session state](/neru/providers/state#initializing-the-state-provider) which is specific to a session and has a TTL.

## Method Signature
```javascript
neru.getGlobalState()
```

## Getting Global State

```tabbed_content
source: _tutorials_tabbed_content/neru/code-snippets/global/instance-state
```