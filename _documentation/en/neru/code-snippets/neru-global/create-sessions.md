---
title: Create NeRu Sessions
description: How to create NeRu Sessions
navigation_weight: 4
---

# Create NeRu Sessions

There are many ways to create a new [NeRu session](/neru/guides/sessions.md) depending on your use case.

## Create a Session

You can create a session by optionally specifying a TTL, if one is not specified the default value of 7 days will be used. If you want a global session that does not expire, you can use the [global session](/neru/code-snippets/neru-global/get-sessions/javascript#global-session).

### Method Signature
```javascript
createSession(ttl?: number)
```

### Creating a Session

```tabbed_content
source: _tutorials_tabbed_content/neru/code-snippets/global/create-session
```

## Create a Session with and ID

You can create a session specifying an ID.

### Method Signature
```javascript
createSessionWithId(id: string)
```

### Creating a Session with an ID

```tabbed_content
source: _tutorials_tabbed_content/neru/code-snippets/global/create-session-id
```