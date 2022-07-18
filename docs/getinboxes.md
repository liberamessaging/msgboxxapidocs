---
title: Get Inboxes
layout: default
---

## Get Inboxes

To retrieve all the inboxes that you have access to:

`GET https://api.msgboxx.io/inboxes`

will return a list of all inboxes that have access to, in most cases this will return a single ionbox. Optional parameters to filter the results down include apiAccountId as detailed in the swagger documentation.

`HTTP 200 OK`

```json
{
  "items": [
    {
        "inboxId": "84ca7cae-b7aa-47da-bafa-b9bb4acd2c7e",
        "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
        "name": "my inbox",
        "dateTime": "2022-07-05T20:13:22.263Z"
    }
  ],
  "paging": {
    "recordCount": 1
  }
}
```

