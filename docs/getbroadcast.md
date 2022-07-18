---
title: Get a Broadcast
layout: default
---

## Get a Broadcast

To retrieve a single broadcast you will need to already know the broadcastId from a previous search. 

`GET https://api.msgboxx.io/broadcast/{broadcastId}`

for this example: 

`GET https://api.msgboxx.io/broadcast/84ca7cae-b7aa-47da-bafa-b9bb4acd2c7e`

which will return the broadcast on the system. 

`HTTP 200 OK`

```json
{
    "broadcastId": "84ca7cae-b7aa-47da-bafa-b9bb4acd2c7e",
    "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "contactId": "a38f0fc8-cb26-4266-bbd9-35eb8dbd6947",
    "messageId": "ce2400ec-f80a-4509-bcd3-5aa5a96a4bdf",
    "message": "Hi Jack, thanks for the conversation earlier about the 2 bedroom house in Swindon lets catch up soon.",
    "status": "Sent",
    "dateTime": "2022-07-05T20:13:22.263Z"
}
```
