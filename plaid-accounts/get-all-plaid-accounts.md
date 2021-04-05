---
description: >-
  Use this endpoint to get a list of all synced Plaid accounts associated with
  the user's account.
---

# Get all Plaid accounts

Plaid Accounts are individual bank accounts that you have linked to Lunch Money via Plaid. You may link one bank but one bank might contain 4 accounts. Each of these accounts is a Plaid Account.

{% api-method method="get" host="https://dev.lunchmoney.app" path="/v1/plaid\_accounts" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "plaid_accounts": [
    {
      "id": 91,
      "date_linked": "2020-01-28T14:15:09.111Z",
      "name": "401k",
      "type": "brokerage",
      "subtype": "401k",
      "mask": "7468",
      "institution_name": "Vanguard",
      "status": "inactive",
      "last_import": "2019-09-04T12:57:09.190Z",
      "balance": "12345.6700",
      "currency": "usd",
      "balance_last_update": "2020-01-27T01:38:11.862Z",
      "limit": null
    },
    {
      "id": 89,
      "date_linked": "2020-01-28T14:15:09.111Z",
      "name": "Freedom",
      "type": "credit",
      "subtype": "credit card",
      "mask": "1973",
      "institution_name": "Chase",
      "status": "active",
      "last_import": "2019-09-04T12:57:03.250Z",
      "balance": "0.0000",
      "currency": "usd",
      "balance_last_update": "2020-01-27T01:38:07.460Z",
      "limit": 15000
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

