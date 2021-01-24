# Get all tags

{% api-method method="get" host="https://dev.lunchmoney.app" path="/v1/tags" %}
{% api-method-summary %}
Get all tags
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
[
    {
        "id": 1807,
        "name": "Wedding",
        "description": "All wedding-related expenses"
    },
    {
        "id": 1808,
        "name": "Honeymoon",
        "description": "All honeymoon-related expenses"
    }
]
```

{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}
