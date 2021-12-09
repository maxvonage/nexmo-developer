---
title: Messages Provider Guides
description: Various actions of the Messages provider
navigation_weight: 1
---

# Messages Provider Guides

## Initialize messages api
```javascript
import { neru, providers } from "neru-alpha";

const instance = neru.createInstance();
const messagesAPI = new providers.Messages(instance);
```

## Send text message
```javascript
await messagesApi.sendText(
            { type: "sms", number: "<from number>" },
            { type: "sms", number: "<to number>" },
            "<your message here>"
          )
          .execute();
```

## Listen for incoming messages
```javascript
await messagesApi.listenMessages(
      { type: "sms", number: "<from number>" },
      { type: "sms", number: "<to number>" },
      "<your endpoint>" // e.g. "onInboundMessages"
).execute()
                  
```