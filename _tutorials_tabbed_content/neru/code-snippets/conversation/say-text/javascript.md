---
title: Javascript
language: javascript
menu_weight: 1
---

```javascript
app.post("/onCall", async (req, res) => {
    const session = neru.createSession();
    const voice = new Voice(session);
    const conversation = await voice.createConversation();
  
    await conversation.acceptInboundCall(req.body).execute();
    
    const body = new SayTextBody();
    body.text = 'Hi Alice!';
    await conversation.sayText(body).execute();

    res.status(200);
});
```