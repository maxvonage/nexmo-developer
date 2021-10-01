---
title: Generate a JWT
description: In this step you learn how to generate a JWT.
---

# Generate a JWT

The Conversation API is authenticated using Jason Web Tokens (JWTs).

> **NOTE:** Please replace `APP_ID` with your application ID.
`private.key` is the key associated with your application.

You can generate a JWT with the following command:

``` bash
JWT="$(nexmo jwt:generate private.key exp=$(($(date +%s)+86400)) application_id=APP_ID)"
```

> **NOTE:** Your JWT will be valid for one day.

You can then view your JWT with:

``` bash
echo $JWT
```

> **TIP:** You can verify your JWT at [jwt.io](https://jwt.io).
