---
title: Get a Single Message
layout: default
---

## Get a Single Message

To retrieve a single message you will need to already know the messageId from a previous search. 

`GET https://api.msgboxx.io/message/{messageId}`

for this example:

`GET https://api.msgboxx.io/message/ce2400ec-f80a-4509-bcd3-5aa5a96a4bdf`

which will return the message on the system. 

`HTTP 200 OK`

```json
{
    "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "contactId": "17b5c90a-7465-1097-b2db-66afa62c963f",
    "messageId": "ce2400ec-f80a-4509-bcd3-5aa5a96a4bdf",
    "message": "Hi John, that sounds good progress, kepp me informed please. ",
    "status": "Sent",
    "dateTime": "2022-07-05T20:13:22.263Z"
}
```
