# Contact Groups

[[toc]]

Refer below to a documentation on how to manage your team inbox ``conversations`` via our REST API's.

### Get a list of your conversations by phone number

```http
GET /conversations/{{waba_id}}
Authorization: Bearer your_bearer_token_here
Host: https://developer.shauriwave.com/integration
Content-Type: application/json
```
#### sample payload
```json
{
  "limit": 10
}
```
| Parameter | Required | Description                                                     |
|-----------|----------|-----------------------------------------------------------------|
| `limit`   | No       | Limit the no of results to return.                              |
| `waba_id` | Yes      | The ``waba_id`` of one of your already onboarded phone numbers. |


#### sample response
````json
[
  {
    "name": "John Doe",
    "phone": "254706019415",
    "latest_message": {
      "context": {
        "message_id": "wamid.HBgMMjU0NzA2MDE5NDE1FQIAEhggRTIyREVBRUVBRjVFMjE0N0Q1NzNEOTBERjBCRjVEMkQA"
      },
      "delivered": true,
      "from": "254706019415",
      "id": "wamid.HBgMMjU0NzA2MDE5NDE1FQIAEhggRTIyREVBRUVBRjVFMjE0N0Q1NzNEOTBERjBCRjVEMkQA",
      "interactive": {
        "nfm_reply": {
          "body": "Sent",
          "name": "flow",
          "response_json": "{\"flow_token\":\"unused\",\"no_of_guests\":\"2\",\"reservation_time\":\"12:10\",\"full_name\":\"tabby\",\"email_address\":\"\",\"reservation_date\":\"1711037763293\",\"notes\":\"notes\"}"
        },
        "type": "nfm_reply"
      },
      "read": true,
      "replied": false,
      "sent": true,
      "timestamp": "1711037783",
      "type": "interactive"
    },
    "unread_messages_count": 0
  }
]
````

### Get a conversation messages

```http
GET /messages/{{chat_id}}
Authorization: Bearer your_bearer_token_here
Host: https://developer.shauriwave.com/integration
Content-Type: application/json
```
#### sample payload
```json
{
  "limit": 10,
  "waba_id": "115393944782556"
}
```
| Parameter | Required | Description                                                                                 |
|-----------|----------|---------------------------------------------------------------------------------------------|
| `limit`   | No       | Limit the no of results to return.                                                          |
| `waba_id` | Yes      | The ``waba_id`` linked to the currently conversation your are trying to access it messages. |
| `chat_id` | Yes      | The ``chat_id`` of one of your existing conversations refer to get a list of conversations. |



#### sample response
````json
[
  {
    "delivered": true,
    "from": "15550027500",
    "id": "wamid.HBgMMjU0NzExNTM2NzMzFQIAERgSMEE1Njc4MTE5MDQxM0RDNURCAA==",
    "read": true,
    "replied": false,
    "sent": true,
    "sent_by": {
      "id": 88,
      "name": "UNTITLED_1711475541970",
      "type": "broadcast"
    },
    "template": {
      "category": "MARKETING",
      "components": [
        {
          "format": "video",
          "type": "HEADER",
          "video": {
            "link": "https://storage.googleapis.com/shauriwave.appspot.com/messages/templates/file_1711475576.mp4?GoogleAccessId=firebase-adminsdk-kkb9o%40shauriwave.iam.gserviceaccount.com&Expires=4867149176&Signature=qwxU9NKYtvrkVZQ7uEhmxALLg4GBqJ6e2cF8g%2FxrE%2BmSmBiEetEIPCvW20XRybGqY0l2v8nCE%2BjpWfuiqF9rS%2B%2B5MClowIIppwDY4%2FJb6wgNF8APdmUrTE8J8NuzHOrJ3%2FdfG72v2xVsinSnHSyP1pF3ExGYeYCwUt%2F9IXnRd8Zms4NnOUhAS3Qv6zFgR7mNOeUPQzHja0WEtTMMeDth4w60bxEROQ%2FB7Rih2v%2BdYA86QSkAUZx%2FvoOn39aT1p9aIfiIGBykPPAv6bf2kqL9BTZsVGIaztjWWjlQG5oVhEEayPCg9hzoUgVymjHpa%2F%2BIjbCBVEEqZV78HNTTQeNfpw%3D%3D"
          }
        },
        {
          "text": "Hello *Shauri Wave*\nIt's quite easy to onboard a phone number on *Shauri Wave*. What you will need.\n\n✅ A phone number *NOT* currently *ACTIVE* on *WHATSAPP* and can receive verification messages\n✅ An active *FACEBOOK* account that you are an *ADMIN*.\n✅ A *VALID* business with a working website and email address.\n\nThats it 🚀",
          "type": "BODY"
        },
        {
          "text": "Powered by shauriwave.com",
          "type": "FOOTER"
        },
        {
          "buttons": [
            {
              "text": "Onboard phone",
              "type": "URL",
              "url": "https://app.shauriwave.com/phone-number"
            }
          ],
          "type": "BUTTONS"
        }
      ],
      "id": "1510019636215917",
      "language": "en",
      "name": "onboard_phone",
      "status": "APPROVED"
    },
    "timestamp": 1711475587,
    "type": "template"
  },
  {
    "context": {
      "body": "Hello <b>Shauri Wave</b>\nIt's quite easy to onboard a phone number on <b>Shauri Wave</b>. What you will need.\n\n✅ A phone number <b>NOT</b> currently <b>ACTIVE</b> on <b>WHATSAPP</b> and can receive verification messages\n✅ An active <b>FACEBOOK</b> account that you are an <b>ADMIN</b>.\n✅ A <b>VALID</b> business with a working website and email address.\n\nThats it 🚀",
      "message_id": "wamid.HBgMMjU0NzExNTM2NzMzFQIAERgSMEE1Njc4MTE5MDQxM0RDNURCAA==",
      "type": "template"
    },
    "delivered": false,
    "failed": true,
    "from": "15550027500",
    "id": "wamid.HBgMMjU0NzExNTM2NzMzFQIAERgSMDBCMjg5MTA0QjBBOEM4MTFEAA==",
    "read": true,
    "replied": false,
    "sent": false,
    "sent_by": {
      "id": 1,
      "name": "Vacay Experience",
      "type": "user"
    },
    "text": {
      "body": "hello"
    },
    "timestamp": 1711543513,
    "type": "text"
  }
]
````