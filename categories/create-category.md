---
description: Use this endpoint to create a single category
---

# Create category

{% api-method method="post" host="https://dev.lunchmoney.app" path="/v1/categories" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="name" type="string" required=true %}
Name of category. Must be between 1 and 40 characters.
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
Description of category. Must be less than 140 categories.
{% endapi-method-parameter %}

{% api-method-parameter name="is\_income" type="boolean" required=false %}
Whether or not transactions in this category should be treated as income. Defaults to false.
{% endapi-method-parameter %}

{% api-method-parameter name="exclude\_from\_budget" type="boolean" required=false %}
Whether or not transactions in this category should be excluded from budgets. Defaults to false.
{% endapi-method-parameter %}

{% api-method-parameter name="exclude\_from\_totals" type="boolean" required=false %}
Whether or not transactions in this category should be excluded from calculated totals. Defaults to false.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Returns the ID of the newly-created category
{% endapi-method-response-example-description %}

```
{
    "category_id": 26213
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{ error: 'Missing category name.' }
{ error: 'Category name must be less than 40 characters.' }
{ error: 'Category description must be less than 140 characters.' }
{ error: 'Operation error occurred. Please try again or contact support@lunchmoney.app for assistance.' }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

