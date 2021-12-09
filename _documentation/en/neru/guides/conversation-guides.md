---
title: Conversation Provider Guides
description: Various actions of the Conversation provider
navigation_weight: 2
---

# Conversation Provider Guides


## Initialize conversation api
```javascript
import { neru, providers } from "neru-alpha";

const instance = neru.createInstance();
const conversationAPI = new providers.Conversation(instance);
```

## Create a conversation
```javascript
const conversation = await conversationAPI.createConversation("<unique name>", "<display name>");
```

## Add a listener for inbound calls
```javascript
const callee = {
  type: "phone",
  number: "<lvn number>",
};

const caller = {
  type: "phone",
  number: "<caller number>", // starting with a country code, e.g. 44xxx
};

// "onInboundCall" is a name of your endpoint
await conversationAPI.onInboundCall("onInboundCall", callee, caller).execute();
```

## Accept an inbound call
```javascript
// "onInboundCall" is an endpoint you specified above
router.post("/onInboundCall", async (req, res) => {
  const event = req.body;
  ...
  await conversation.acceptInboundCall(event).execute();
  ...
```

## Add a listener for DTMF 

```javascript
// "onDTMF" is a name of your endpoint
await conversation.onDTMF('onDTMF').execute();
```

## Collect DTMF digits
```javascript
router.post("/onDTMF", async (req, res) => {
  const event = req.body;
  console.log(`User input is: ${event.body.digit}`);
  ...
```

## Create a user
```javascript
const user = await conversation.addUser("<user name>").execute();
```

## Make an outbound phone call
```javascript
await conversation
  .inviteMember(userName, {
    type: "phone",
    from: {
      number: "<lvn number>",
      type: "phone",
    },
    to: {
      number: "<callee number>",
      type: "phone",
    },
  })
  .execute();
```

## Use of TTS (text-to-speech)
```javascript
await conversation.onMemberJoined("onMemberJoined", "<userName>").execute();

router.post('/onMemberJoined', async (req, res) => {
  ...
  await conversation.sayText({ text: "<your text here>" }).execute();
  ...
```

## Play a stream
```javascript
router.post('/onMemberJoined', async (req, res) => {
  ...
  await conversation
      .playStream(
        {
          stream_url: [
            "https://nexmo-community.github.io/ncco-examples/assets/voice_api_audio_streaming.mp3",
          ],
          level: 1, // Set the audio level of the audio stream: min=-1 max=1 increment=0.1.
          loop: 1, // The number of times to repeat audio. Set to 0 to loop infinitely.
        },
        req.body.body.member_id
      )
      .execute();
  ...

```