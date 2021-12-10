---
title: Handle inbound DTMF
description: In this step you learn how to handle inbound DTMF with NeRu.
---

# Handle inbound DTMF

Much like the previous step you now need to define a route for the DTMF listener defined in the previous step. Add the follow code to the bottom of the `index.js` file:

```javascript
router.post("/onDTMF", async (req, res) => {
  const event = req.body;
  const digit = event.body.digit;
  const instance = neru.getInstanceFromRequest(req);
  const state = instance.getState();
  const conversationApi = new providers.Conversation(instance);

  const conversationId = await state.get('conversationId');
  const conversation = conversationApi.getConversation(conversationId);

  conversation.sayText({text: `I received ${digit}`})


  res.status(200);
});

startListening();

export { router };
```

The above code gets the digit pressed from the incoming request's body and creates a NeRu instance using that request. Like before, the NeRu instance is used to create state and conversations provider. The conversation ID is retried from the state and used to create a conversation object which then uses text-to-speech to relay the digits pressed to the caller.

Outside of the function it called the `startListening` function from earlier and exports the router.

## Deploy an instance of your project

By deploying you are creating an instance of your project - a running service that is built from the current version of the code with the current configuration (neru.yml). You can deploy your project by running:

```sh
neru-cli deploy
```

Once complete you can now call your Vonage Number and hear the digits you press!