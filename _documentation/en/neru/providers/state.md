---
title: State
description: The State Provider
navigation_weight: 1
---

## State Provider

The State provider allows you to store data on NeRu for your project instance to use. The state provider has a key-value store at its root. As well as  lists and maps with various operations you can perform on them.

### Initializing the State Provider

To can access the state provider from a NeRu Instance.

```javascript
import { neru } from "neru-alpha";

const instance = neru.createInstance();
const state = instance.getState();
```

On subsequent calls to your code you want to make sure that you are using the same instance to have access to your state. You can do so by initializing your instance from an incoming request.

```javascript
router.post("/onMessage", async (req, res, next) => {
  try {
    const instance = neru.getInstanceFromRequest(req);
    const state = instance.getState();

    // Handle incoming message
  } catch (error) {
    next(error);
  }
});
```