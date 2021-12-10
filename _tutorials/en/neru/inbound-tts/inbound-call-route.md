---
title: Handle inbound calls
description: In this step you learn how to handle inbound calls with NeRu.
---

# Handle inbound calls

As mentioned in the previous step, you need to define a route to handle your inbound calls. Add the following code below your existing code in the `index.js` file:

```javascript
router.post("/onInboundCall", async (req, res) => {
  const instance = neru.getInstanceFromRequest(req);
  const conversationAPI = new providers.Conversation(instance);

  const conversation = await conversationAPI.createConversation(
    `unique_id_${uuid()}`,
    `ConversationDisplayName`
  );
  await conversation.acceptInboundCall(req.body).execute();
  await conversation
    .sayText({
      text: `Hello user, your number is: ${req.body.body.channel.from.number}`,
    })
    .execute();

  res.status(200);
});

startListening();

export { router };
```

The above code create a NeRu instance, but this time it creates it from the incoming request. The instance is used to create a conversation provider, which is then used to create a [conversation](/conversation/concepts/conversation).

This conversation is used to accept the inbound call and then the `sayText` function allows you to great your called with text-to-speech. Outside of the function it called the `startListening` function from earlier and exports the router.

## Deploy an instance of your project

By deploying you are creating an instance of your project - a running service that is built from the current version of the code with the current configuration (neru.yml). You can deploy your project by running:

```sh
neru-cli deploy
```

Once complete you can now call your Vonage Number and hear the greeting!