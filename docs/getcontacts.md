---
title: Get Contacts
layout: default
---

## Get Contacts

Before you can send a session message or broadcast a template messsage you will need a contactId.

Next we need the details of the contact we are going to send it to. To retrieve a contact from the above api account with the mobile number +447902111123 we do the following

`GET https://api.msgboxx.io/contact`

which will return the list of all the contacts on the system across all apiAccounts. See below for further filtering options. 

`HTTP 200 OK`

```json
{
  "items": [
    {
      "contactId": "17b5c90a-7465-1097-b2db-66afa62c963f",
      "mobileNumber": "+447902111123",
      "name": "Test Customer",
      "status": "Subscribed",
      "email": "customer@somewhere.com",
      "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "datetime": "2022-07-05T20:09:58.341Z"
    },
    {
      "contactId": "a38f0fc8-cb26-4266-bbd9-35eb8dbd6947",
      "mobileNumber": "+447902875098",
      "name": "Miss Customer",
      "status": "Subscribed",
      "email": "miss@somewhereelse.com",
      "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "datetime": "2022-07-05T20:09:58.341Z"
    }
  ],
  "paging": {
    "recordCount": 2
  }
}
```

Keep a note of the contactId returned.

Filtering options are available to limit results just to a single apiAccount, or to a mobile number, or to both as per below. 

`GET https://api.msgboxx.io/contact?apiAccountId=3fa85f64-5717-4562-b3fc-2c963f66afa6&mobileNumber=447902111123`