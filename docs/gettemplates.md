---
title: Get Templates
layout: default
---

## Get Templates

To retrieve all the templates that you have access to:

`GET https://api.msgboxx.io/template`

will return a list of all templates on the system, in most cases this will be a small list (around 15) and will bave paging info in it. 

`HTTP 200 OK`

```json
{
  "items": [
    {
      "templateId": "0bbadd13-0e3f-4ebb-9f65-9e6ee460d7ba",
      "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "status": "Approved",
      "name": "follow_up",
      "templateText": "{% raw  %}Hi {{1}}, thanks for the conversation earlier about {{2}} lets catch up soon.{% endraw %}",
      "templateExample": "Hi John, thanks for the conversation earlier about the msgboxx platform lets catch up soon.",
      "dateTime": "2022-07-05T20:13:22.260Z"
    }
  ],
  "paging": {
    "recordCount": 1
  }
}
```

