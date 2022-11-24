---
title: Python
language: python
menu_weight: 1
---

```python
session = neru.createSession()
voice = Voice(session)

vonageNumber = ChannelPhoneEndpoint('447000000000')
to = ChannelPhoneEndpoint('447000000001')

ncco = [
            {
                'action': 'talk',
                'text': 'Hi! This is a call made by the Voice API and NeRu'
            }
    ]

await voice.vapiCreateCall(vonageNumber, [to], ncco).execute()
```