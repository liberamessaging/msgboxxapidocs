---
title: Get an Inbox
layout: default
---

## Get an Inbox

To retrieve a single inbox you will need to already know the inboxId from a previous search. 

`GET https://api.msgboxx.io/inbox/{inboxId}`

for this example:

`GET https://api.msgboxx.io/inbox/84ca7cae-b7aa-47da-bafa-b9bb4acd2c7e`

which will return the inbox on the system. 

`HTTP 200 OK`

```json
{
    "inboxId": "84ca7cae-b7aa-47da-bafa-b9bb4acd2c7e",
    "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "name": "my inbox",
    "dateTime": "2022-07-05T20:13:22.263Z"
}
```
