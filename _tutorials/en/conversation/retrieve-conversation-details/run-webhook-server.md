---
title: Learn how to run your webhook server
description: Learn how to run your webhook server
---

# Run the Webhook Server

You need to run a webhook server to help obtain the Conversation ID for the in-progress call.

Please use the following Python code:

``` python
from flask import Flask, request, jsonify
from pprint import pprint

app = Flask(__name__)

ncco = [{
        "action": "connect",
        "endpoint": [{
            "type": 'phone',
            "number": 'TO_NUMBER'
        }]
}]

@app.route("/webhooks/answer")
def answer_call():
    params = request.args
    pprint(params)
    return jsonify(ncco)

if __name__ == '__main__':
    app.run(port=3000)
```

> **IMPORTANT:** You need to replace `TO_NUMBER` with the number of your second phone, phone 2 (Bob).

Run this webhook server locally with:

``` bash
python3 app.py
```
