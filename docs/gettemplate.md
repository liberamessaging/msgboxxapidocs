---
title: Get a Single Template
layout: default
---

## Get a Single Template

To retrieve a single template you will need to already know the templateId from a previous search. 

`GET https://api.msgboxx.io/template/{templateId}`

for this example:

`GET https://api.msgboxx.io/template/0bbadd13-0e3f-4ebb-9f65-9e6ee460d7ba`

which will return the message on the system. 

`HTTP 200 OK`

```json
{
      "templateId": "0bbadd13-0e3f-4ebb-9f65-9e6ee460d7ba",
      "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "status": "Approved",
      "name": "follow_up",
      "templateText": "{% raw  %}Hi {{1}}, thanks for the conversation earlier about {{2}} lets catch up soon.{% endraw %}",
      "templateExample": "Hi John, thanks for the conversation earlier about the msgboxx platform lets catch up soon.",
      "dateTime": "2022-07-05T20:13:22.260Z"
}
```
