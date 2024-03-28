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