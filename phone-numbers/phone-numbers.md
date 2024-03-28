# Phone Numbers

[[toc]]

Refer below to a documentation on how to manage your already onboarded ``phone numbers`` via our REST API's.

### List your already onboarded phone numbers

```http
GET /phone-numbers
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
| Parameter | Required | Description                        |
|-----------|----------|------------------------------------|
| `limit`   | No       | Limit the no of results to return. |

#### sample response
````json
[
  {
    "uuid": "aa23da15-1c2e-4edd-8262-15ae837b4c2c",
    "name": "Test Number",
    "phone_number": "+15550027500",
    "account_id": "111600408499020",
    "waba_id": "115393944782556",
    "registered": true
  }
]
````

### Get a phone number

```http
GET /phone-numbers/{{waba_id}}
Authorization: Bearer your_bearer_token_here
Host: https://developer.shauriwave.com/integration
Content-Type: application/json
```
| Parameter | Required | Description                                                     |
|-----------|----------|-----------------------------------------------------------------|
| `waba_id` | Yes      | The ``waba_id`` of one of your already onboarded phone numbers. |

#### sample response
````json
{
  "uuid": "aa23da15-1c2e-4edd-8262-15ae837b4c2c",
  "name": "Test Number",
  "phone_number": "+15550027500",
  "account_id": "111600408499020",
  "waba_id": "115393944782556",
  "registered": true
}
````