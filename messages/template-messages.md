# Template Messages

[[toc]]

Please consult the documentation below for guidance on sending marketing or utility messages templates through our Rest API. If you haven't created one, please proceed to your app's dashboard at https://appp.shauriwave.com/phone-numbers to create a template.

![Preview](./img/template_msg.png)

## Message templates components
- `Optional Header`: A template header may consist of text, image, video, audio, or file types.
- `Required Body`: The template body must be text-only.
- `Footer (Optional)`: The template footer, if included, can be text-based and is not mandatory for sending a template message.
- `Optional Buttons`: Template buttons, if utilized, can be of type array, with the only required type being URL dynamic buttons.

## Sample template components
```json
[
  {
    "type": "HEADER",
    "format": "IMAGE",
    "example": {
      "header_handle": [
        "https://scontent.whatsapp.net/v/t61.29466-34/428008456_1198718407774379_7020962117414608334_n.jpg?ccb=1-7&_nc_sid=8b1bef&_nc_eui2=AeFzv_j4-AXJsZ3gmD922Pc0zSPbmDKZ0h7NI9uYMpnSHsG0T6ro5-sRVyJcMHKO9gpxlrU3UdokDomsaVqYuYuB&_nc_ohc=BYMeeH5dwVQAb6gnvhQ&_nc_pt=5&_nc_ht=scontent.whatsapp.net&edm=AH51TzQEAAAA&oh=01_ASCstRgLgFWfzBsS0YYWmDc3mva9-4yTELT8sGYDsoNYIw&oe=66361954"
      ]
    }
  },
  {
    "text": "Hey *{{1}}*,\n\nWe've noticed your passion for adventure! Get ready for an exciting journey! Join us on April 12th for an incredible adventure experience in the *Aberdares National Park*.\n\nSecure your spot now and don't miss out!",
    "type": "BODY",
    "example": {
      "body_text": [
        ["Derrick"]
      ]
    }
  },
  {
    "type": "BUTTONS",
    "buttons": 
    [
      {
        "url": "https://vacayexperience.travel/{{1}}",
        "text": "Book package",
        "type": "URL",
        "example": [
          "https://vacayexperience.travel/packages/booking/d260e95e-35f1-4e8b-a5a0-140c9b3f28a0"
        ]
      }
    ]
  }
]
```


Before sending out a template as a message, we conduct validation checks to ensure compliance. Rest assured, if the parameters of the sent template do not match the requirements, we will notify you via a 422 error response, outlining the necessary adjustments.

## Send a template message

```http
POST /message/template/{waba_id}
Authorization: Bearer your_bearer_token_here
Host: https://developer.shauriwave.com/integration
Content-Type: application/json
```
#### sample payload
```json
{
  "template_id": "390350103807391",
  "phone": "254711536733",
  "parameters": {
    "header":"https://fourthprofile.sfo3.cdn.digitaloceanspaces.com/posts/95c683ce-0759-4540-89b2-50520bfd6899/whatsapp_flows.jpeg",
    "body": [ "Derrick"],
    "buttons": ["https://shauriwave.com/home","https://shauriwave.com/apply"]
  },
  "save_message": false
}
```
| Parameter            | Required | Description                                                                                        |
|----------------------|----------|----------------------------------------------------------------------------------------------------|
| `template_id`        | Yes      | Your authentication message template id                                                            |
| `phone`              | Yes      | Recipient phone number. Include the country calling code                                           |
| `save_message`       | No       | Boolean flag indicating whether to save the message sent as a chat                                 |
| `waba_id`            | Yes      | The ``waba_id`` of one of your already onboarded phone numbers associated with the template message. |
| `parameters.header`  | No       | Required when a template has a required header variable (text,image,video,audio,document)          |
| `parameters.body`    | No       | Required when a template has required body variables (text only)                                   |
| `parameters.buttons` | No       | Required when a template contains dynamic url buttons or copy coupon code buttons.                 |

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
  "message": "The parameters.header field is required."
}
````
````json
{
  "message": "The parameters.header field must be a valid URL."
}
````
````json
{
  "message": "Invalid file detected please provide a valid image link"
}
````
````json
{
  "message": "Url https://shauriwave.coem/home provided does not match the base url: https://shauriwave.com/{{1}}"
}
````


