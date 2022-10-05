---
title: Get Messages
layout: default
---

## Get Messages

To retrieve all the messages that you have access to:

`GET https://api.msgboxx.io/message`

will return a list of all messages that have been sent, in most cases this will be a big list and will bave paging info in it. Optional parameters to filter the results down include apiAccountId, inboxId, and contactId, conversationId as detailed in the swagger documentation. By default the filtering will filter on last 24 hours unless fromDate and toDate are provided.

`HTTP 200 OK`

```json
{
  "items": [
    {
      "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "contactId": "17b5c90a-7465-1097-b2db-66afa62c963f",
      "messageId": "ce2400ec-f80a-4509-bcd3-5aa5a96a4bdf",
      "message": "Hi John, that sounds good progress, keep me informed please. ",
      "status": "Sent",
      "dateTime": "2022-07-05T20:13:22.263Z"
    }
  ],
  "paging": {
    "recordCount": 1
  }
}
```
