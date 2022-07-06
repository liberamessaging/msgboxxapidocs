---
title: Get A Contact
layout: default
---

## Get Contacts

To retrieve a single contact you will need to already know the contactId from a previous search. 

`GET https://api.msgboxx.io/contact/a38f0fc8-cb26-4266-bbd9-35eb8dbd6947`

which will return the list contact on the system. 

`HTTP 200 OK`

```json
{
    "contactId": "a38f0fc8-cb26-4266-bbd9-35eb8dbd6947",
    "mobileNumber": "+447902875098",
    "name": "Miss Customer",
    "status": "Subscribed",
    "email": "miss@somewhereelse.com",
    "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
    "datetime": "2022-07-05T20:09:58.341Z"
}
```
