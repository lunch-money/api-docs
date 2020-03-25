# Insert transactions

{% api-method method="post" host="https://dev.lunchmoney.app" path="/v1/transactions" %}
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
List of transactions to insert \(see below\)
{% endapi-method-parameter %}

{% api-method-parameter name="apply\_rules" type="boolean" %}
If true, will apply account’s existing rules to the inserted transactions. Defaults to false.
{% endapi-method-parameter %}

{% api-method-parameter name="check\_for\_recurring" type="boolean" %}
If true, will check new transactions for occurrences of new monthly expenses. Defaults to false.
{% endapi-method-parameter %}

{% api-method-parameter name="debit\_as\_negative" type="boolean" %}
If true, will assume negative amount values denote expenses and positive amount values denote credits. Defaults to false.  
  
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Upon success, IDs of inserted transactions will be returned in an array.
{% endapi-method-response-example-description %}

```text
{
    ids: [54, 55, 56, 57]
}

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
An array of errors will be returned denoting reason why parameters were deemed invalid.
{% endapi-method-response-example-description %}

```text
{ error:
   [ 'Transaction 0 is missing date.',
     'Transaction 0 is missing amount.',
     'Transaction 1 status must be either cleared or uncleared: null' ] }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Insert Transaction object

| Key | Type |  | Description |
| :--- | :--- | :--- | :--- |
| date | string | Required | Must be in ISO 8601 format \(YYYY-MM-DD\) |
| category\_id | number | Optional | Unique identifier for associated category\_id. Category must be associated with the same account and must not be a category group. |
| payee | string | Optional | Max 140 characters |
| amount | number \| string | Required | Numeric value of amount. i.e. $4.25 should be denoted as 4.25 |
| currency | string | Optional, defaults to user account's primary currency | Three-letter lowercase currency code must exist in our database |
| asset\_id | number | Optional | Unique identifier for associated asset \(manually-managed account\). Asset must be associated with the same account. |
| recurring\_id | number | Optional | Unique identifier for associated recurring expense. Recurring expense must be associated with the same account. |
| notes | string | Optional | Max 350 characters |
| status | string | Optional, defaults to `uncleared` | Must be either `cleared` or `uncleared`. Defaults to `uncleared` If recurring\_id is provided, the status will automatically be set to `recurring` or `recurring_suggested` depending on the type of recurring\_id |
| external\_id | string | Optional | User-defined external ID for transaction. Max 75 characters. External IDs must be unique within the same asset\_id. |

## 

