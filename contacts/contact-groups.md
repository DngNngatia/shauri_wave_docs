# Contact Groups

[[toc]]

Refer below to a documentation on how to manage your ``contact groups`` via our REST API's.

### Create a contact group

```http
POST /contact-groups
Authorization: Bearer your_bearer_token_here
Host: https://developer.shauriwave.com/integration
Content-Type: application/json
```
#### sample payload
```json
{
  "name": "Client List"
}
```
| Parameter | Required                     | Description                 |
|-----------|-------------------------|-----------------------------|
| `name`    | Yes | Name of your contact group. |

#### sample response
````json
{
  "message": "Contact group created successfully!"
}
````

### List your contact groups

```http
GET /contact-groups
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
    "uuid": "f288b054-6235-4d3b-8fd5-71ee74eb3f93",
    "name": "Client List"
  }
]
````

### Delete a contact group

```http
DELETE /contact-groups/{{contact_group_uuid}}
Authorization: Bearer your_bearer_token_here
Host: https://developer.shauriwave.com/integration
Content-Type: application/json
```
| Parameter | Required | Description                                           |
|-----------|----------|-------------------------------------------------------|
| `contact_group_uuid`   | Yes      | The contact group uuid of one of your contact groups. |

#### sample response
````json
{
  "message": "Contact group deleted successfully!"
}
````