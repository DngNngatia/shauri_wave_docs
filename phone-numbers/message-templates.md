# Contact Groups

[[toc]]

Message templates are interactive messages designed for sending to your customers using the WhatsApp API.

Refer below to a documentation on how to manage your ``message templates`` via our REST API's.

### Create a contact
Please use our [dashboard](https://app.shauriwave.com/phone-numbers) to create a message template or your developer console.

### List your message templates

```http
GET /message-templates/{{waba_id}}
Authorization: Bearer your_bearer_token_here
Host: https://developer.shauriwave.com/integration
Content-Type: application/json
```
#### sample payload
```json
{
  "limit": 10,
  "id": "1510019636215917"
}
```
| Parameter | Required | Description                                           |
|-----------|----------|-------------------------------------------------------|
| `limit`   | No       | Limit the no of results to return.                    |
| `id`      | No       | Pass this to get a specific message template by id.   |
| `name`    | No       | Pass this to get a specific message template by name. |
| `waba_id` | Yes      | The ``waba_id`` of one of your already onboarded phone numbers. |




#### sample response
````json
{
  "data": [
    {
      "name": "onboard_phone",
      "language": "en",
      "status": "APPROVED",
      "category": "MARKETING",
      "id": "1510019636215917"
    }
  ],
  "paging": {
    "cursors": {
      "before": "MAZDZD",
      "after": "MAZDZD"
    },
    "next": "https://graph.facebook.com/v15.0/111600408499020/message_templates?fields=name%2Clanguage%2Cstatus%2Ccategory%2Cid&limit=1&after=MAZDZD"
  }
}
````
