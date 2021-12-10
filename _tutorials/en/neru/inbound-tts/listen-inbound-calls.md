---
title: Listen for inbound calls
description: In this step you learn how to listen for inbound calls with NeRu.
---

# Listen for inbound calls

To listen for inbound calls you will need to use the [Conversation Provider](/neru/providers/conversations). Add the following function below your existing code in the `index.js` file:

```javascript
const startListening = async () => {
  const instance = neru.createInstance();
  const conversationAPI = new providers.Conversation(instance);
  const { contact: vonageNumber } = JSON.parse(process.env.neru_configurations);

  const callee = {
    type: "phone",
    number: vonageNumber,
  };

  const caller = {
    type: "phone",
    number: "*",
  };

  await conversationAPI.onInboundCall("onInboundCall", callee, caller).execute();
}
```

The above code creates a NeRu [instance](neru/concepts/instance) then using that to create a conversation provider. Then it gets your Vonage number from your NeRu configurations as defined in your `neru.yml` file. Then the `onInboundCall` listener on the conversation provider is used to listen for incoming calls to your Vonage number. Note how the caller object is using a wildcard for the number property, this means that any incoming call will be listened for, you can specify a number here to filter on. 

The `onInboundCall` function takes a route name as its first parameter. So when your Vonage number gets and incoming call, NeRu will make an call to this route, so next you will define it. 