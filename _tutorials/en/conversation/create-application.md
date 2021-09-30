---
title: Create a Conversation Application
description: In this step you learn how to create a Conversation Application.
meta_title: Create a Conversation application for the Vonage APIs
meta_description: In this step you learn how to create a Conversation Application.
---

# Create your Application

You will need to create a Vonage Application if you have not already done so.

> **NOTE:** Replace `demo` with your own app name in the following code.

``` bash
nexmo app:create "Conversation App" http://demo.ngrok.io/webhooks/answer http://demo.ngrok.io/webhooks/event --keyfile private.key
```

> **NOTE:** Make a note of the generated Application ID (`APP_ID`), you will need this when you generate a Jason Web Token (JWT).
