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

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

