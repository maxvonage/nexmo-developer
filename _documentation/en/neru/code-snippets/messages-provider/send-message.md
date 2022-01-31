---
title: Send a Message
description: How to send a message with the Messages provider
navigation_weight: 1
---

# Send a Message

The Messages provider's `sendText` function allows you to send a message using the [Messages API](/messages/overview).

## Method signature
```javascript
sendText(from: Contact, to: Contact, message: string)
```

### Types

This function using the NeRu `Contact` type for the sender and recipient of the message.

`Contact`:

* `type`: (String) The type of the contact, e.g. phone.
* `number`: (String) A phone number in in the [E.164](https://en.wikipedia.org/wiki/E.164) format.
* `id`: (Optional String) An ID number, for use with Facebook Messenger.

## Sending a message

```tabbed_content
source: _tutorials_tabbed_content/neru/code-snippets/messages/send-text
```