---
title: Get NeRu Sessions
description: How to get NeRu Sessions
navigation_weight: 5
---

# Get NeRu Sessions

There are many ways to get existing [NeRu sessions](/neru/guides/sessions.md) depending on your use case. 

## Global Session

The global session is a session which is tied to the life of your instance. This is used for the [global state](/neru/code-snippets/neru-global/instance-state).

### Method Signature
```javascript
neru.getGlobalSession()
```

### Getting your Global Session

```tabbed_content
source: _tutorials_tabbed_content/neru/code-snippets/global/get-global-session
```

## Get Session by ID

If you have a session ID you can use it to retrieve a session.

### Method Signature
```javascript
neru.getSessionById(id: string)
```

### Getting your Session by ID

```tabbed_content
source: _tutorials_tabbed_content/neru/code-snippets/global/get-session
```

## Get Session from a Request

If you have an incoming  request from the NeRu platform which has the `x-neru-sessionid` header, you can use it to retrieve a session.

### Method Signature
```javascript
neru.getSessionFromRequest(req: IRequest)
```

`IRequest` is an interface which is satisfied by an object which has a `headers` property e.g. `req.body` in request.

### Getting your Session from a Request

```tabbed_content
source: _tutorials_tabbed_content/neru/code-snippets/global/get-session-request
```