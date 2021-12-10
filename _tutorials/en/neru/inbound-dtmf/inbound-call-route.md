---
title: Handle inbound calls
description: In this step you learn how to handle inbound calls with NeRu.
---

# Handle inbound calls

As mentioned in the previous step, you need to define a route to handle your inbound calls. Add the following code below your existing code in the `index.js` file:

```javascript
router.post("/onInboundCall", async (req, res) => {
  const instance = neru.createInstance();
  const state = instance.getState();
  const conversationAPI = new providers.Conversation(instance);
  const conversationId = `unique_id_${uuid()}`;

  const conversation = await conversationAPI.createConversation(
    conversationId,
    `ConversationDisplayName`
  );

  await state.set('conversationId', conversationId);

  // accept an incoming call
  await conversation.acceptInboundCall(req.body).execute();

  await conversation.sayText({ text: "Please, use your keyboard to provide your date of birth" }).execute();

  // add a listener for dtmf input
  await conversation.onDTMF('onDTMF').execute();

  res.status(200);
});
```

The above code create a NeRu instance, but this time it creates it from the incoming request. The instance is used to create a state and conversation provider, which is then used to create a [conversation](/conversation/concepts/conversation) with a unique ID. The conversation ID is then stored with the state provider for use later.

This conversation is used to accept the inbound call and then the `sayText` function allows you to ask the caller for their date of birth. Finally it adds a new listener for DTMF events on this conversation with a route, `onDTMF`. 