---
description: >-
  Use this endpoint to update a single transaction. You may also use this to
  split an existing transaction.
---

# Update transaction

{% api-method method="put" host="https://dev.lunchmoney.app" path="/v1/transactions/:transaction\_id" %}
{% api-method-summary %}
Update transaction
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="transaction" type="array" required=true %}
Updates to transaction matching ID \(see Update Transaction object below\)
{% endapi-method-parameter %}

{% api-method-parameter name="debit\_as\_negative" type="boolean" required=false %}
If true, will assume negative amount values denote expenses and positive amount values denote credits. Defaults to false.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
If a split was part of the request, an array of newly-created split transactions will be returned.
{% endapi-method-response-example-description %}

```text
{
    updated: true,
    split: [58, 59]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Array of errors will be returned if field\(s\) are invalid.
{% endapi-method-response-example-description %}

```text
{ error:
   [ 'This transaction doesn't exist or you don't have access to it.' ] }

{ error:
   [ 'You cannot change the amount for this transaction because it was automatically imported.',
     'You cannot assign an asset_id for this transaction because it was automatically imported.' ] }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% tabs %}
{% tab title="Update Transaction object" %}
### Update Transaction object

| Key |  | Type |  | Description |
| :--- | :--- | :---: | :--- | :--- |
| **date** |  | string |  | Must be in ISO 8601 format \(YYYY-MM-DD\). |
| **category\_id** |  | number |  | Unique identifier for associated category\_id. Category must be associated with the same account and must not be a category group. |
| **payee** |  | string |  | Max 140 characters |
| **amount** |  | number \| string |  | You may only update this if this transaction was not created from an automatic import, i.e. if this transaction is not associated with a plaid\_account\_id |
| **currency** |  | string |  | You may only update this if this transaction was not created from an automatic import, i.e. if this transaction is not associated with a plaid\_account\_id. Defaults to user account's primary currency. |
| **asset\_id** |  | number |  | Unique identifier for associated asset \(manually-managed account\). Asset must be associated with the same account. You may only update this if this transaction was not created from an automatic import, i.e. if this transaction is not associated with a plaid\_account\_id |
| **recurring\_id** |  | number |  | Unique identifier for associated recurring expense. Recurring expense must be associated with the same account. |
| **notes** |  | string |  | Max 350 characters |
| **status** |  | string |  | Must be either `cleared` or `uncleared`. Defaults to `uncleared` If recurring\_id is provided, the status will automatically be set to `recurring` or `recurring_suggested` depending on the type of recurring\_id. Defaults to `uncleared`. |
| **external\_id** |  | string |  | User-defined external ID for transaction. Max 75 characters. External IDs must be unique within the same asset\_id. You may only update this if this transaction was not created from an automatic import, i.e. if this transaction is not associated with a plaid\_account\_id |
| **split** |  | array of Split objects |  | Defines the split of a transaction. You may not split an already-split transaction, recurring transaction, or group transaction. |
{% endtab %}

{% tab title="Split object" %}
### Split object

<table>
  <thead>
    <tr>
      <th style="text-align:left">Key</th>
      <th style="text-align:left"></th>
      <th style="text-align:center">Type</th>
      <th style="text-align:left"></th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>date</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:center">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Must be in ISO 8601 format (YYYY-MM-DD)</p>
        <p><em>Required.</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>category_id</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:center">number</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Unique identifier for associated category_id. Category must be associated
          with the same account.</p>
        <p><em>Required.</em>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>notes</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:center">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>amount</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:center">number | string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Individual amount of split. Currency will inherit from parent transaction.
          All amounts must sum up to parent transaction amount.</p>
        <p><em>Required.</em>
        </p>
      </td>
    </tr>
  </tbody>
</table>
{% endtab %}
{% endtabs %}

