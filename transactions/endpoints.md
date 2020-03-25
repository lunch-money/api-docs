# Endpoints

{% api-method method="get" host="https://api.cakes.com" path="/v1/transactions" %}
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

{% api-method-parameter name="debit\_as\_negative" type="boolean" %}
Pass in true if you’d like expenses to be returned as negative amounts and credits as positive amounts.
Defaults to false.
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


{% api-method method="get" host="https://api.cakes.com" path="/v1/transactions/:transaction_id" %}
{% api-method-summary %}
Get single transaction
{% endapi-method-summary %}

{% api-method-description %}
Returns a single Transaction object
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="debit\_as\_negative" type="boolean" %}
Pass in true if you’d like expenses to be returned as negative amounts and credits as positive amounts.
Defaults to false.
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


{% api-method method="post" host="https://api.cakes.com" path="/v1/transactions" %}
{% api-method-summary %}
Insert transactions
{% endapi-method-summary %}

{% api-method-description %}
Bulk-insert transactions
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="transactions" type="array" required=true %}
List of transactions to insert.
{% endapi-method-parameter %}

{% api-method-parameter name="apply\_rules" type="boolean" %}
If true, will apply account’s existing rules to the inserted transactions.
Defaults to false.
{% endapi-method-parameter %}

{% api-method-parameter name="check\_for\_recurring" type="boolean" %}
If true, will check new transactions for occurences of new monthly expenses.
Defaults to false.
{% endapi-method-parameter %}

{% api-method-parameter name="debit\_as\_negative" type="boolean" %}
If true, will assume negative amount values denote expenses and positive amount values denote credits.
Defaults to false.
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



{% api-method method="put" host="https://api.cakes.com" path="/v1/transactions/:transaction_id" %}
{% api-method-summary %}
Update transaction
{% endapi-method-summary %}

{% api-method-description %}
Bulk-insert transactions
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="transaction" type="array" required=true %}
Updates to transaction with ID {transaction_id}
{% endapi-method-parameter %}

{% api-method-parameter name="debit\_as\_negative" type="boolean" %}
If true, will assume negative amount values denote expenses and positive amount values denote credits.
Defaults to false.
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
