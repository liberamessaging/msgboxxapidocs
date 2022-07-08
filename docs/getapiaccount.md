---
title: Get an API Account
layout: default
---

## Get an API Account

Before you can send any messages in the platform you need to know the apiAccountid that you are going to send from. The apiAccountId is linked to the phone number on WhatsApp that you will be sending from, and is a one to one relationship with an inbox. 

To retrieve all a single api accounts that you can perform the following:

`GET https://api.msgboxx.io/apiaccount/{apiAccountId}`

and this specific example we have 

`GET https://api.msgboxx.io/apiaccount/3fa85f64-5717-4562-b3fc-2c963f66afa6`

this will return the apiAccountId

`HTTP 200 OK`

```json
{
  "items": [
    {
      "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "phoneNumber": "+447777123156",
      "name": "My Company",
      "datetime": "2022-07-05T20:08:48.453Z"
    }
  ],
  "paging": {
    "recordCount": 1
  }
}
```

In order to send the message or broadcast you will require the apiAccountId guid above.