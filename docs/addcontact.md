---
title: Add A Contact
layout: default
---

## Add A Contact

To create a new contact in the system you will first need to know which apiAccountId you wish to associate it with. 

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

You will need the apiAccountId from the above, then we post to the contact endpoint

`POST https://api.msgboxx.io/contact/`

with the following body

```json
{
  "mobileNumber": "+447771123456",
  "name": "Brian Tester",
  "status": "Presubscribed",
  "email": null,
  "apiAccountid": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
}
```

which will return the following

`HTTP 201 CREATED`

```json
{
  "contactId": "03f9e6b6-b243-4576-8515-84f43f03a59f",
  "mobileNumber": "+447771123456",
  "name": "Brian Tester",
  "status": "Presubscribed",
  "email": null,
  "apiAccountid": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "datetime": "2022-07-06T20:01:11.567Z"
}
```

The contactId can then be used for sending them session and broadcast messages.
