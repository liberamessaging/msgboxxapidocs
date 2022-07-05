---
title: Send Broadcast
layout: default
---

## Sending a Broadcast 

Sending a broadcast message has a number of mandatory data items including the api account you are sending from, the contact you are sending to, the template you are sending, and the actual text you are sending. These examples assume you only have access to a single inbox and api account.

First retrieve the api account that you are sending from. 

`GET https://api.msgboxx.io/apiaccount`

will return a list of all api accounts you have access to, in most cases this will be a list of one. 

`HTTP 200 OK 
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
}`

In order to send the broadcast you will require the apiAccountId guid above. 

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
      "apiAccountid": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "datetime": "2022-07-05T20:09:58.341Z"
    }
  ],
  "paging": {
    "recordCount": 1
  }
}
```

Keep a note of the contactId returned.

Then we need the template. Templates are configured on the system and have to be approved by WhatsApp. They are standard phrases which have placeholders in them which need to be replaced. You may have a template called follow_up which has the following text in it

`Hi {{1}}, thanks for the conversation earlier about {{2}} lets catch up soon. `

Which once the placeholders are replaced could look like

`Hi John, thanks for the conversation earlier about the msgboxx platform lets catch up soon. `

To get the list of templates on the system 

`GET https://api.msgboxx.io/templates`

will return the following

`HTTP 200 OK
{
  "items": [
    {
      "templateId": "0bbadd13-0e3f-4ebb-9f65-9e6ee460d7ba",
      "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "status": "Approved",
      "name": "follow_up",
      "templateText": "Hi {{1}}, thanks for the conversation earlier about {{2}} lets catch up soon.",
      "templateExample": "Hi John, thanks for the conversation earlier about the msgboxx platform lets catch up soon. ",
      "dateTime": "2022-07-05T20:13:22.260Z"
    }
  ],
  "paging": {
    "recordCount": 1
  }
}`

Now we have the templates we can perform any placeholder replacements required, and send the template message.

`POST https://api.msgboxx.io/broadcast`

with the following body

`{
  "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "contactId": "17b5c90a-7465-1097-b2db-66afa62c963f",
  "templateId": "0bbadd13-0e3f-4ebb-9f65-9e6ee460d7ba",
  "message": "Hi John, thanks for the conversation earlier about the msgboxx platform lets catch up soon. "
}`

which will return the following

`HTTP 201 CREATED
{
  "broadcastId": "d81eba15-3983-437a-9f8c-1ff1c79686ed",
  "apiAccountId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "contactId": "17b5c90a-7465-1097-b2db-66afa62c963f",
  "messageId": "ce2400ec-f80a-4509-bcd3-5aa5a96a4bdf",
  "message": "Hi John, thanks for the conversation earlier about the msgboxx platform lets catch up soon. ",
  "status": "Sent",
  "dateTime": "2022-07-05T20:13:22.263Z"
}`

Note due to the async nature of the platform you will always be returned the broadcastId, but not always get the messageId, nessage and status fields until the message is actually sent.

To check on the status of your broadcast message you can perform the following which wil return the same data as above.

`GET https://api.msgboxx.io/broadcast/d81eba15-3983-437a-9f8c-1ff1c79686ed`

The status will cycle between Pending, Sent, Delivered, and Read.