# Wallet

[[toc]]

Refer below to a documentation on how to manage you ``wallet`` via our REST API's.

## Get your account balance

```http
GET /wallet-balance
Authorization: Bearer your_bearer_token_here
Host: https://developer.shauriwave.com/integration
Content-Type: application/json
```
#### sample response
````json
{
  "balance": "26.0",
  "currency": "USD"
}
````

## Get your wallet transactions

```http
GET /wallet-transactions
Authorization: Bearer your_bearer_token_here
Host: https://developer.shauriwave.com/integration
Content-Type: application/json
```
#### sample payload
```json
{
  "per_page": 10
}
```
| Parameter | Required | Description                       |
|-----------|----------|-----------------------------------|
| `per_page`   | No       | Transactions per page default 10. |

#### sample response
````json
{
  "current_page": 1,
  "data": [
    {
      "id": 156,
      "uuid": "1a12b3eb-a33e-4d92-aee4-86215f94035c",
      "type": "Debit",
      "reference": "cffb5b20eae0f23be51b28d400faff25",
      "currency_id": 3,
      "amount": 0.0225,
      "usd_amount": 0.0225,
      "description": "Conversation type marketing debit reference cffb5b20eae0f23be51b28d400faff25 at Tue, Mar 26, 2024 5:53 PM",
      "created_at": "2024-03-26T16:32:20.000000Z",
      "currency": {
        "id": 3,
        "name": "USD",
        "code": "USD"
      }
    },
    {
      "id": 155,
      "uuid": "d34f161a-1177-4867-9b15-b171ab129af7",
      "type": "Debit",
      "reference": "6d7a729b0108aecbdf7fa37f603f8c80",
      "currency_id": 3,
      "amount": 0.0225,
      "usd_amount": 0.0225,
      "description": "Conversation type marketing debit reference 6d7a729b0108aecbdf7fa37f603f8c80 at Tue, Mar 26, 2024 8:00 AM",
      "created_at": "2024-03-25T12:41:21.000000Z",
      "currency": {
        "id": 3,
        "name": "USD",
        "code": "USD"
      }
    }
  ],
  "first_page_url": "https://developer.shauriwave.com/integration/wallet-transactions?page=1",
  "from": 1,
  "last_page": 76,
  "last_page_url": "https://developer.shauriwave.com/integration/wallet-transactions?page=76",
  "links": [
    {
      "url": null,
      "label": "&laquo; Previous",
      "active": false
    },
    {
      "url": "https://developer.shauriwave.com/integration/wallet-transactions?page=1",
      "label": "1",
      "active": true
    },
    {
      "url": "https://developer.shauriwave.com/integration/wallet-transactions?page=2",
      "label": "2",
      "active": false
    },
    {
      "url": "https://developer.shauriwave.com/integration/wallet-transactions?page=3",
      "label": "3",
      "active": false
    },
    {
      "url": "https://developer.shauriwave.com/integration/wallet-transactions?page=4",
      "label": "4",
      "active": false
    },
    {
      "url": "https://developer.shauriwave.com/integration/wallet-transactions?page=5",
      "label": "5",
      "active": false
    },
    {
      "url": "https://developer.shauriwave.com/integration/wallet-transactions?page=6",
      "label": "6",
      "active": false
    },
    {
      "url": "https://developer.shauriwave.com/integration/wallet-transactions?page=7",
      "label": "7",
      "active": false
    },
    {
      "url": "https://developer.shauriwave.com/integration/wallet-transactions?page=8",
      "label": "8",
      "active": false
    },
    {
      "url": "https://developer.shauriwave.com/integration/wallet-transactions?page=9",
      "label": "9",
      "active": false
    },
    {
      "url": "https://developer.shauriwave.com/integration/wallet-transactions?page=10",
      "label": "10",
      "active": false
    },
    {
      "url": null,
      "label": "...",
      "active": false
    },
    {
      "url": "https://developer.shauriwave.com/integration/wallet-transactions?page=75",
      "label": "75",
      "active": false
    },
    {
      "url": "https://developer.shauriwave.com/integration/wallet-transactions?page=76",
      "label": "76",
      "active": false
    },
    {
      "url": "https://developer.shauriwave.com/integration/wallet-transactions?page=2",
      "label": "Next &raquo;",
      "active": false
    }
  ],
  "next_page_url": "https://developer.shauriwave.com/integration/wallet-transactions?page=2",
  "path": "https://developer.shauriwave.com/integration/wallet-transactions",
  "per_page": 2,
  "prev_page_url": null,
  "to": 2,
  "total": 151
}
````