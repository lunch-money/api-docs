---
description: >-
  Use this endpoint to retrieve a list of recurring expenses to expect for a
  specified period.
---

# Get recurring expenses

Every month, a different set of recurring expenses is expected. This is because recurring expenses can be once a year, twice a year, every 4 months, etc.

If a recurring expense is listed as “twice a month”, then that recurring expense will be returned twice, each with a different billing date based on when the system believes that recurring expense transaction is to be expected. If the recurring expense is listed as “once a week”, then that recurring expense will be returned in this list as many times as there are weeks for the specified month.

In the same vein, if a recurring expense that began last month is set to “Every 3 months”, then that recurring expense will not show up in the results for this month.

{% api-method method="get" host="https://dev.lunchmoney.app" path="/v1/recurring\_expenses" %}
{% api-method-summary %}
Get recurring expenses
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="start\_date" type="string" required=false %}
Accepts a string in ISO-8601 short format. Whatever your start date, the system will automatically return recurring expenses expected for that month. For instance, if you input `2020-01-25`, the system will return recurring expenses which are to be expected between `2020-01-01` to `2020-01-31`. Defaults to the first day of the current month.
{% endapi-method-parameter %}

{% api-method-parameter name="debit\_as\_negative" type="boolean" required=false %}
Pass in true if you’d like expenses to be returned as negative amounts and credits as positive amounts. Defaults to false.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Returns a list of Recurring Expense objects
{% endapi-method-response-example-description %}

```javascript
{
  "recurring_expenses": [
    {
      "id": 264,
      "start_date": "2020-01-01",
      "end_date": null,
      "cadence": "twice a month",
      "payee": "Test 5",
      "amount": "-122.0000",
      "currency": "cad",
      "created_at": "2020-01-30T07:58:43.944Z",
      "description": null,
      "billing_date": "2020-01-01",
      "type": "cleared",
      "original_name": null,
      "source": "manual",
      "plaid_account_id": null,
      "asset_id": null,
      "transaction_id": null
    },
    {
      "id": 262,
      "start_date": "2020-01-01",
      "end_date": null,
      "cadence": "monthly",
      "payee": "Test 2",
      "amount": "-32.4500",
      "currency": "usd",
      "created_at": "2020-01-30T07:58:43.921Z",
      "description": "Test description 2",
      "billing_date": "2020-01-03",
      "type": "cleared",
      "original_name": null,
      "source": "manual",
      "plaid_account_id": null,
      "asset_id": null,
      "transaction_id": null
    },
    {
      "id": 264,
      "start_date": "2020-01-01",
      "end_date": null,
      "cadence": "twice a month",
      "payee": "Test 5",
      "amount": "-122.0000",
      "currency": "cad",
      "created_at": "2020-01-30T07:58:43.944Z",
      "description": null,
      "billing_date": "2020-01-15",
      "type": "cleared",
      "original_name": null,
      "source": "manual",
      "plaid_account_id": null,
      "asset_id": null,
      "transaction_id": null
    }
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{ "error": "Invalid start_date. Must be in format YYYY-MM-DD" }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

