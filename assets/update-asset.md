# Update asset

{% api-method method="put" host="https://dev.lunchmoney.app" path="/v1/assets/:id" %}
{% api-method-summary %}
Update asset
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="type\_name" type="string" required=false %}
Must be one of: `cash`, `credit`, `investment`, `other`, `real estate`, `loan`, `vehicle`, `cryptocurrency`, `employee compensation`
{% endapi-method-parameter %}

{% api-method-parameter name="subtype\_name" type="string" required=false %}
Max 25 characters
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
Max 45 characters
{% endapi-method-parameter %}

{% api-method-parameter name="balance" type="string" required=false %}
Numeric value of the current balance of the account. Do not include any special characters aside from a decimal point!
{% endapi-method-parameter %}

{% api-method-parameter name="balance\_as\_of" type="string" required=false %}
Has no effect if `balance` is not defined. If `balance` is defined, but `balance_as_of` is not supplied or is invalid, current timestamp will be used.
{% endapi-method-parameter %}

{% api-method-parameter name="currency" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="institution\_name" type="string" required=false %}
Max 50 characters
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
    "id": 12,
    "type_name": "cash",
    "subtype_name": "savings",
    "name": "TD Savings Account",
    "balance": "28658.5300",
    "balance_as_of": "2020-03-10T05:17:23.856Z",
    "currency": "cad",
    "institution_name": "TD Bank",
    "created_at": "2019-08-10T22:46:19.486Z"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{ errors:
   [ 'type_name must be one of: cash, credit, investment, other, real estate, loan, vehicle, cryptocurrency, employee compensation' ] }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

