# Authentication Messages

[[toc]]

Please consult the documentation below for guidance on sending authentication messages through our Rest API. If you haven't yet generated an authentication message, please proceed to your app's dashboard at https://appp.shauriwave.com/phone-numbers to create a template.

![Preview](./img/auth_msg.png)

## Send an authentication message

```http
POST /message/template/authentication/{waba_id}
Authorization: Bearer your_bearer_token_here
Host: https://developer.shauriwave.com/integration
Content-Type: application/json
```
#### sample payload
```json
{
  "template_id": "396424149762513",
  "phone": "254711536733",
  "code": "200500",
  "save_message": true
}
```
| Parameter      | Required | Description                                                                                                      |
|----------------|----------|------------------------------------------------------------------------------------------------------------------|
| `template_id`  | Yes      | Your authentication message template id                                                                          |
| `phone`        | Yes      | Recipient phone number. Include the country calling code                                                         |
| `code`         | Yes      | Your authentication code                                                                                         |
| `save_message` | No       | Boolean flag indicating whether to save the message sent as a chat                                               |
| `waba_id` | Yes      | The ``waba_id`` of one of your already onboarded phone numbers associated with the authentication template used. |


#### sample response
````json
{
  "message": "Message sent successfully!",
  "data": {
    "message_id": "wamid.HBgMMjU0NzExNTM2NzMzFQIAERgSRTFDNDBGOUIzRDFEMjA2QkZCAA=="
  }
}
````

#### sample error responses
````json
{
  "message": "We could not find an authentication template with id 39642414976251 please confirm it exists and its categorised as an authentication template."
}
````
````json
{
  "message": "The phone field is required."
}
````
