---
description: >-
  Use this endpoint to get a list of all categories associated with the user's
  account.
---

# Get all categories

{% api-method method="get" host="https://dev.lunchmoney.app" path="/v1/categories" %}
{% api-method-summary %}
Get all categories
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
  "categories": [
    {
      "id": 83,
      "name": "Test 1",
      "description": "Test description",
      "is_income": false,
      "exclude_from_budget": true,
      "exclude_from_totals": false,
      "updated_at": "2020-01-28T09:49:03.225Z",
      "created_at": "2020-01-28T09:49:03.225Z",
      "is_group": true,
      "group_id": null
    },
    {
      "id": 84,
      "name": "Test 2",
      "description": null,
      "is_income": true,
      "exclude_from_budget": false,
      "exclude_from_totals": true,
      "updated_at": "2020-01-28T09:49:03.238Z",
      "created_at": "2020-01-28T09:49:03.238Z",
      "is_group": false,
      "group_id": 83
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

