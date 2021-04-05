---
description: Use this endpoint to retrieve details about a specific transaction by ID.
---

# Get single transaction

{% api-method method="get" host="https://dev.lunchmoney.app" path="/v1/transactions/:transaction\_id" %}
{% api-method-summary %}
Get transaction
{% endapi-method-summary %}

{% api-method-description %}
Returns a single Transaction object
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="debit\_as\_negative" type="boolean" %}
Pass in true if you’d like expenses to be returned as negative amounts and credits as positive amounts. Defaults to false.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "id": 31,
    "date": "2019-02-04",
    "payee": "Shell",
    "amount": "960.0000",
    "currency": "jpy",
    "notes": null,
    "category_id": 22,
    "recurring_id": null,
    "asset_id": null,
    "plaid_account_id": null,
    "status": "cleared",
    "is_group": false,
    "group_id": null,
    "parent_id": null,
    "has_children": null,
    "external_id": null
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{ "error": "Transaction ID not found." }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

