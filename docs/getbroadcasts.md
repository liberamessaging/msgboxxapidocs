---
title: Get Broadcasts
layout: default
---

## Get Broadcasts

To retrieve all the broadcasts that you have access to:

`GET https://api.msgboxx.io/broadcast`

will return a list of all broadcasts that have been sent, in most cases this will be a big list and will bave paging info in it. Optional parameters to filter the results down include apiAccountId, inboxId, and contactId as detailed in the swagger documentation.

`HTTP 200 OK`

```json
{
  "items": [
    {
        "broadcastId": "84ca7cae-b7aa-47da-bafa-b9bb4acd2c7e",
        "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
        "contactId": "a38f0fc8-cb26-4266-bbd9-35eb8dbd6947",
        "messageId": "ce2400ec-f80a-4509-bcd3-5aa5a96a4bdf",
        "message": "Hi Jack, thanks for the conversation earlier about the 2 bedroom house in Swindon lets catch up soon.",
        "status": "Sent",
        "dateTime": "2022-07-05T20:13:22.263Z"
    }
  ],
  "paging": {
    "recordCount": 1
  }
}
```

