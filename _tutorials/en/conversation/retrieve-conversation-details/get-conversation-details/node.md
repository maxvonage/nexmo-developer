---
title: Get Conversation Details
description: Get the Conversation object
meta_title: Get Conversation Details
meta_description: Get the Conversation Object
---

# Get the Conversation Details

Use the code below to retrieve details of the Conversation object for your current call.

> **NOTE:** You will need to replace `$CONVERSATION_ID` by your ID and `$JWT` with the JWT you created.

Use this API call to get your Conversation object:

``` code_snippets
source: '_examples/conversation/conversation/get-conversation'
```

The API call will give you a response similar to the following:

``` json
{
    "uuid": "CON-bc643220-2542-499a-892e-c982c4150c06",
    "name": "NAM-1b2c4274-e3f2-494e-89c4-46856ee84a8b",
    "timestamp": {
        "created": "2018-10-25T09:26:18.999Z"
    },
    "sequence_number": 8,
    "numbers": {},
    "properties": {
        "ttl": 172800,
        "video": false
    },
    "members": [
        {
            "member_id": "MEM-f44c872e-cba9-444f-88ae-0bfa630865a6",
            "user_id": "USR-33a51f4d-d06b-42f6-a525-90d2859ab9f6",
            "name": "USR-33a51f4d-d06b-42f6-a525-90d2859ab9f6",
            "state": "JOINED",
            "timestamp": {
                "joined": "2018-10-25T09:26:30.334Z"
            },
            "channel": {
                "type": "phone",
                "id": "797168e24c19a3c45e74e05b10fef2b5",
                "from": {
                    "type": "phone",
                    "number": "447700000001"
                },
                "to": {
                    "type": "phone",
                    "number": "447700000002"
                },
                "leg_ids": [
                    "797168e24c19a3c45e74e05b10fef2b5"
                ]
            },
            "initiator": {
                "joined": {
                    "isSystem": true
                }
            }
        },
        {
            "member_id": "MEM-25ccda92-839d-4ac6-a7b2-de310224878b",
            "user_id": "USR-b9948493-be4a-4b36-bb4d-c96bcc2af85b",
            "name": "vapi-user-f59c1ff26c0543fdb6c02fd30617a1c0",
            "state": "JOINED",
            "timestamp": {
                "invited": "2018-10-25T09:26:19.385Z",
                "joined": "2018-10-25T09:26:30.270Z"
            },
            "invited_by": "USR-b9948493-be4a-4b36-bb4d-c96bcc2af85b",
            "channel": {
                "type": "phone",
                "id": "30cecc87-7ac9-4d03-910a-e9d69558263c",
                "from": {
                    "number": "Unknown",
                    "type": "phone"
                },
                "leg_ids": [
                    "30cecc87-7ac9-4d03-910a-e9d69558263c"
                ],
                "to": {
                    "number": "447700000001",
                    "type": "phone"
                },
                "cpa": false,
                "preanswer": false,
                "ring_timeout": 60000,
                "cpa_time": 5000,
                "max_length": 7200000
            },
            "initiator": {
                "invited": {
                    "isSystem": true
                }
            }
        }
    ],
    "_links": {
        "self": {
            "href": "https://api.nexmo.com/beta/conversations/CON-bc643220-2542-499a-892e-c982c4150c06"
        }
    }
}
```

See [Conversation](/conversation/concepts/conversation) for more information.

You can now hang up phone 1 (Alice) and phone 2 (Bob) to terminate the call.
