# Endpoints

{% api-method method="get" host="https://api.cakes.com" path="/v1/cakes/:id" %}
{% api-method-summary %}
Get all transactions
{% endapi-method-summary %}

{% api-method-description %}
Returns list of Transaction objects
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="start\_date" type="string" %}
Denotes the beginning of the time period to fetch transactions for.  
Defaults to beginning of current month.  
Required if end\_date exists.
{% endapi-method-parameter %}

{% api-method-parameter name="end\_date" type="string" %}
Denotes the end of the time period you'd like to get transactions for.  
Defaults to end of current month.  
Required if start\_date exists.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}

{% api-method-body-parameters %}
{% api-method-parameter name="Test body param" type="string" required=false %}
Derp derp
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```
{    "name": "Cake's name",    "recipe": "Cake's recipe name",    "cake": "Binary cake"}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{    "message": "Ain't no cake like that."}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



