---
title: Send Message
layout: default
---

## Sending a Message

Sending a session message has a number of mandatory data items including the api account you are sending from, the contact you are sending to, and the actual text you are sending. These examples assume you only have access to a single inbox and api account.

First retrieve the api account that you are sending from.

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

In order to send the message you will require the apiAccountId guid above.

Next we need the details of the contact we are going to send it to. To retrieve a contact from the above api account with the mobile number +447902111123 we do the following

`GET https://api.msgboxx.io/contact?apiAccountId=3fa85f64-5717-4562-b3fc-2c963f66afa6&mobileNumber=447902111123`

which will return the following

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
    }
  ],
  "paging": {
    "recordCount": 1
  }
}
```

Keep a note of the contactId returned.

Now we have the detials we can send the message

`POST https://api.msgboxx.io/message`

with the following body

```json
{
  "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "contactId": "17b5c90a-7465-1097-b2db-66afa62c963f",
  "message": "Hi John, that sounds good progress, kepp me informed please. "
}
```

which will return the following

`HTTP 201 CREATED`

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

Note due to the asynchronous nature of the platform the status will update as the message is sent, delivered and read.

To check on the status of your message you can perform the following which wil return the same data as above.

`GET https://api.msgboxx.io/message/ce2400ec-f80a-4509-bcd3-5aa5a96a4bdf`

The status will cycle between Pending, Sent, Delivered, and Read.
