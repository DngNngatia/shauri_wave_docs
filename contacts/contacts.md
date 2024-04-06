# Contact Groups

[[toc]]

Refer below to a documentation on how to manage your ``contacts`` via our REST API's.

## Create a contact
```http
POST /contacts
Authorization: Bearer your_bearer_token_here
Host: https://developer.shauriwave.com/integration
Content-Type: application/json
```
#### sample payload
```json
{
  "name": "John Doe",
  "phone": "+254711536733",
  "contacts_groups" : ["f288b054-6235-4d3b-8fd5-71ee74eb3f93"]
}
```
| Parameter | Required | Description                                                          |
|-----------|----------|----------------------------------------------------------------------|
| `name`    | Yes      | Name of your contact.                                                |
| `phone`   | Yes      | Contact phone number with country calling code.                      |
| `contacts_groups`   | No       | An array of contact groups ``uuid's`` to associate the contact with. |


#### sample response
````json
{
  "message": "Contact created successfully!"
}
````

## List your contacts

```http
GET /contacts
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
    "uuid": "fb3bc4f5-f2dc-4c19-a35f-edd26a924b6c",
    "name": "John Doe",
    "phone_number": "+256711536733",
    "created_at": "2024-03-28T12:40:04.000000Z"
  }
]
````

## List your contacts by a contact group

```http
GET /contact-groups/{{contact_group_uuid}}/contacts
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
| Parameter | Required | Description                                           |
|-----------|----------|-------------------------------------------------------|
| `limit`   | No       | Limit the no of results to return.                    |
| `contact_group_uuid`   | Yes      | The contact group uuid of one of your contact groups. |


#### sample response
````json
[
  {
    "uuid": "fb3bc4f5-f2dc-4c19-a35f-edd26a924b6c",
    "name": "John Doe",
    "phone_number": "+256711536733",
    "created_at": "2024-03-28T12:40:04.000000Z"
  }
]
````
## Get a contact

```http
GET /contacts/{{contact_uuid}}
Authorization: Bearer your_bearer_token_here
Host: https://developer.shauriwave.com/integration
Content-Type: application/json
```
| Parameter | Required | Description                                          |
|-----------|----------|------------------------------------------------------|
| `contact_uuid`   | Yes      | The contact uuid of one of your contact groups. |

#### sample response
````json
{
  "uuid": "fb3bc4f5-f2dc-4c19-a35f-edd26a924b6c",
  "name": "John Doe",
  "phone_number": "+256711536733",
  "created_at": "2024-03-28T12:40:04.000000Z"
}
````

## Delete a contact

```http
DELETE /contacts/{{contact_uuid}}
Authorization: Bearer your_bearer_token_here
Host: https://developer.shauriwave.com/integration
Content-Type: application/json
```
| Parameter | Required | Description                                          |
|-----------|----------|------------------------------------------------------|
| `contact_uuid`   | Yes      | The contact uuid of one of your contact groups. |

#### sample response
````json
{
  "message": "Contact deleted successfully!"
}
````
