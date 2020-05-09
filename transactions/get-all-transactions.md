---
description: Use this endpoint to retrieve all transactions between a date range.
---

# Get all transactions

{% api-method method="get" host="https://dev.lunchmoney.app" path="/v1/transactions" %}
{% api-method-summary %}
Get all transactions
{% endapi-method-summary %}

{% api-method-description %}
Returns list of Transaction objects.  
  
If no query parameters are set, this endpoint will return transactions for the current calendar month \(see `start_date` and `end_date`\)
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="tag\_id" type="number" required=false %}
Filter by tag. Only accepts IDs, not names.
{% endapi-method-parameter %}

{% api-method-parameter name="recurring\_id" type="number" required=false %}
Filter by recurring expense
{% endapi-method-parameter %}

{% api-method-parameter name="plaid\_account\_id" type="number" required=false %}
Filter by Plaid account
{% endapi-method-parameter %}

{% api-method-parameter name="category\_id" type="number" required=false %}
Filter by category. Will also match category groups.
{% endapi-method-parameter %}

{% api-method-parameter name="asset\_id" type="number" required=false %}
Filter by asset
{% endapi-method-parameter %}

{% api-method-parameter name="offset" type="number" required=false %}
Sets the offset for the records returned
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="number" required=false %}
Sets the maximum number of records to return.  
**Note:** the server will not respond with any indication that there are more records to be returned. Please check the response length to determine if you should make another call with an offset to fetch more transactions.
{% endapi-method-parameter %}

{% api-method-parameter name="start\_date" type="string" %}
Denotes the beginning of the time period to fetch transactions for. Defaults to beginning of current month. Required if end\_date exists.
{% endapi-method-parameter %}

{% api-method-parameter name="end\_date" type="string" %}
Denotes the end of the time period you'd like to get transactions for. Defaults to end of current month. Required if start\_date exists.
{% endapi-method-parameter %}

{% api-method-parameter name="debit\_as\_negative" type="boolean" %}
Pass in true if you’d like expenses to be returned as negative amounts and credits as positive amounts. Defaults to false.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Returns a list of transactions.
{% endapi-method-response-example-description %}

```text
{ transactions:
   [ { id: 602,
       date: '2020-01-01',
       payee: 'Starbucks',
       amount: '4.5000',
       currency: 'cad',
       notes: 'Frappuccino',
       category_id: null,
       recurring_id: null,
       asset_id: null,
       plaid_account_id: null,
       status: 'cleared',
       is_group: false,
       group_id: null,
       parent_id: null,
       external_id: null },
     { id: 603,
       date: '2020-01-02',
       payee: 'Walmart',
       amount: '20.9100',
       currency: 'usd',
       notes: null,
       category_id: null,
       recurring_id: null,
       asset_id: 153,
       plaid_account_id: null,
       status: 'uncleared',
       is_group: false,
       group_id: null,
       parent_id: null,
       external_id: 'jf2r3t98o943' } ] }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Errors will be returned in parameters are invalid.
{% endapi-method-response-example-description %}

```text
{ error: 'Both start_date and end_date must be specified.' }
{ error: 'Invalid start_date. Must be in format YYYY-MM-DD' }
{ error: 'Invalid end_date. Must be in format YYYY-MM-DD' }
{ error: 'end_date cannot be same or before start_date' }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

