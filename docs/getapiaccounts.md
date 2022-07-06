---
title: Get API Accounts
layout: default
---

## Get API Accounts

Before you can send any messages in the platform you need to know the apiAccountid that you are going to send from. The apiAccountId is linked to the phone number on WhatsApp that you will be sending from, and is a one to one relationship with an inbox. 

To retrieve all api accounts that you have access to:

`GET https://api.msgboxx.io/apiaccount`

will return a list of all api accounts you have access to, in most cases this will be a list of one.

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

In order to send the a mesasge or broadcast you will require the apiAccountId guid above.