---
description: >-
  Use this endpoint to get a list of all manually-managed assets associated with
  the user's account.
---

# Get all assets

{% api-method method="get" host="https://dev.lunchmoney.app" path="/v1/assets" %}
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

```json
{
  "assets": [
    {
      "id": 72,
      "type_name": "cash",
      "subtype_name": "physical cash",
      "name": "Test Asset 1",
      "balance": "1201.0100",
      "balance_as_of": "2020-01-26T12:27:22.000Z",
      "currency": "cad",
      "status": "active",
      "institution_name": "Bank of Me",
      "created_at": "2020-01-26T12:27:22.726Z"
    },
    {
      "id": 73,
      "type_name": "credit",
      "subtype_name": "credit card",
      "name": "Test Asset 2",
      "balance": "0.0000",
      "balance_as_of": "2020-01-26T12:27:22.000Z",
      "currency": "usd",
      "status": "active",
      "institution_name": "Bank of You",
      "created_at": "2020-01-26T12:27:22.744Z"
    },
    {
      "id": 74,
      "type_name": "vehicle",
      "subtype_name": "automobile",
      "name": "Test Asset 3",
      "balance": "99999999999.0000",
      "balance_as_of": "2020-01-26T12:27:22.000Z",
      "currency": "jpy",
      "status": "active",
      "institution_name": "Bank of Mom",
      "created_at": "2020-01-26T12:27:22.755Z"
    },
    {
      "id": 75,
      "type_name": "loan",
      "subtype_name": null,
      "name": "Test Asset 4",
      "balance": "10101010101.0000",
      "balance_as_of": "2020-01-26T12:27:22.000Z",
      "currency": "twd",
      "status": "active",
      "institution_name": null,
      "created_at": "2020-01-26T12:27:22.765Z"
    }
  ]
}
```

{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

