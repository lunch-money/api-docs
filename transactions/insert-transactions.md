---
description: Use this endpoint to insert many transactions at once.
---

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

{% tabs %}
{% tab title="Insert Transaction object" %}
### Insert Transaction object

<table>
  <thead>
    <tr>
      <th style="text-align:left">Key</th>
      <th style="text-align:left"></th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left"></th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>date</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Must be in ISO 8601 format (YYYY-MM-DD).</p>
        <p><em>Required.</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>amount</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">number | string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Numeric value of amount. i.e. $4.25 should be denoted as 4.25.</p>
        <p><em>Required.</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>category_id</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">number</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Unique identifier for associated category_id. Category must be associated
        with the same account and must not be a category group.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>payee</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Max 140 characters</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>currency</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Three-letter lowercase currency code must exist in our database. Defaults
        to user account&apos;s primary currency.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>asset_id</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">number</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Unique identifier for associated asset (manually-managed account). Asset
        must be associated with the same account.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>recurring_id</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">number</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Unique identifier for associated recurring expense. Recurring expense
        must be associated with the same account.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>notes</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Max 350 characters</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>status</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Must be either <code>cleared</code> or <code>uncleared</code>. If recurring_id
          is provided, the status will automatically be set to <code>recurring</code> or <code>recurring_suggested</code> depending
          on the type of recurring_id.</p>
        <p>Defaults to <code>uncleared</code>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>external_id</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">User-defined external ID for transaction. Max 75 characters. External
        IDs must be unique within the same asset_id.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>tags</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Array of numbers and/or strings</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Passing in a number will attempt to match by ID. If no matching tag ID
          is found, an error will be thrown.</p>
        <p>Passing in a string will attempt to match by string. If no matching tag
          name is found, a new tag will be created.</p>
      </td>
    </tr>
  </tbody>
</table>
{% endtab %}
{% endtabs %}

## 

