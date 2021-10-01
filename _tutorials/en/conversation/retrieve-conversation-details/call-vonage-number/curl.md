---
title: Call the Vonage number.
description: How to Call the Vonage number.
meta_title: Call the Vonage number.
meta_description: How to call a Vonage number.
=======
title: Call Vonage Number
description: Call the Vonage number
---

# Call the Vonage Number

Dial your Vonage Number with phone 1 (Alice). The inbound call is forwarded to your second phone, phone 2 (Bob). Answer the call on phone 2 (Bob). Do not cancel the call yet.

Now check the logging produced by your webhook server. You should see something similar to

``` bash
...
{
   'conversation_uuid': 'CON-bc643220-2542-499a-892e-c982c4150c06',
   'from': '447700000001',
   'to': '447700000002',
   'uuid': '797168e24c19a3c45e74e05b10fef2b5'
}
...
```

You are interested only in the Conversation ID which has the form `CON-<uuid>`. Copy the Conversation ID so you can use it later.
