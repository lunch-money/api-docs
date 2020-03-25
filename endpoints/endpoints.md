# Transactions

## Transaction Object

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Attribute Name</b>
      </th>
      <th style="text-align:left"><b>Type</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">id</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Unique identifier for transaction</td>
    </tr>
    <tr>
      <td style="text-align:left">date</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Date of transaction in ISO 8601 format</td>
    </tr>
    <tr>
      <td style="text-align:left">payee</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>Name of payee</p>
        <p>If recurring_id is not null, this field will show the payee of associated
          recurring expense instead of the original transaction payee</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">amount</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Amount of the transaction in numeric format to 4 decimal places</td>
    </tr>
    <tr>
      <td style="text-align:left">currency</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Three-letter lowercase currency code of the transaction</td>
    </tr>
    <tr>
      <td style="text-align:left">notes</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>User-entered transaction notes</p>
        <p>If recurring_id is not null, this field will be description of associated
          recurring expense</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">category_id</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Unique identifier of associated category (see Categories)</td>
    </tr>
    <tr>
      <td style="text-align:left">asset_id</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">
        <p>Unique identifier of associated manually-managed account (see Assets)</p>
        <p>Note: plaid_account_id and asset_id cannot both exist for a transaction</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">plaid_account_id</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">
        <p>Unique identifier of associated Plaid account (see Plaid Accounts)</p>
        <p>Note: plaid_account_id and asset_id cannot both exist for a transaction</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">status</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">
        <p>One of the following:</p>
        <ul>
          <li>cleared: User has reviewed the transaction</li>
          <li>uncleared: User has not yet reviewed the transaction</li>
          <li>recurring: Transaction is linked to a recurring expense</li>
          <li>recurring_suggested: Transaction is listed as a suggested transaction
            for an existing recurring expense. User intervention is required to change
            this to recurring.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">parent_id</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Exists if this is a split transaction. Denotes the transaction ID of the
        original transaction. Note that the parent transaction is not returned
        in this call.</td>
    </tr>
    <tr>
      <td style="text-align:left">is_group</td>
      <td style="text-align:left">boolean</td>
      <td style="text-align:left">True if this transaction represents a group of transactions. If so, amount
        and currency represent the totalled amount of transactions bearing this
        transaction&#x2019;s id as their group_id. Amount is calculated based on
        the user&#x2019;s primary currency.</td>
    </tr>
    <tr>
      <td style="text-align:left">group_id</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Exists if this transaction is part of a group. Denotes the parent&#x2019;s
        transaction ID</td>
    </tr>
    <tr>
      <td style="text-align:left">tags</td>
      <td style="text-align:left">Tag[]</td>
      <td style="text-align:left">List of tags (see Tag)</td>
    </tr>
    <tr>
      <td style="text-align:left">external_id</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">User-defined external ID for any manually-entered or imported transaction.
        External ID cannot be accessed or changed for Plaid-imported transactions.
        External ID must be unique by asset_id. Max 75 characters.</td>
    </tr>
  </tbody>
</table>## Tag Object

| **Attribute Name** | **Type** | **Description** |
| :--- | :--- | :--- |
| **id** | **number** | **Unique identifier for tag**  |
| **name** | **string** | **User-facing name of tag** |

{% api-method method="get" host="https://dev.lunchmoney.app" path="/v1/transactions" %}
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

{% api-method method="get" host="https://dev.lunchmoney.app" path="/v1/transactions/:transaction\_id" %}
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
Pass in true if you’d like expenses to be returned as negative amounts and credits as positive amounts. Defaults to false.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Returns Transaction object
{% endapi-method-response-example-description %}

```text
{
    "id": 31,
    "date": "2019-02-04",
    "payee": "Shell",
    "amount": "960.0000",
    "currency": "jpy",
    "notes": null,
    "category_id": 22,
    "recurring_id": null,
    "asset_id": null,
    "plaid_account_id": null,
    "status": "cleared",
    "is_group": false,
    "group_id": null,
    "parent_id": null,
    "has_children": null,
    "external_id": null
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a transaction matching this query.
{% endapi-method-response-example-description %}

```text
{ error: 'Transaction ID not found.' }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

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

{% api-method method="put" host="https://api.cakes.com" path="/v1/transactions/:transaction\_id" %}
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
Updates to transaction with ID {transaction\_id}
{% endapi-method-parameter %}

{% api-method-parameter name="debit\_as\_negative" type="boolean" %}
If true, will assume negative amount values denote expenses and positive amount values denote credits. Defaults to false.
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

### Update Transaction object

<table>
  <thead>
    <tr>
      <th style="text-align:left">Key</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left"></th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">date</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Must be in ISO 8601 format (YYYY-MM-DD)</td>
    </tr>
    <tr>
      <td style="text-align:left">category_id</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Unique identifier for associated category_id. Category must be associated
        with the same account and must not be a category group.</td>
    </tr>
    <tr>
      <td style="text-align:left">payee</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Max 140 characters</td>
    </tr>
    <tr>
      <td style="text-align:left">amount</td>
      <td style="text-align:left">number | string</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">You may only update this if this transaction was not created from an automatic
        import, i.e. if this transaction is not associated with a plaid_account_id</td>
    </tr>
    <tr>
      <td style="text-align:left">currency</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Optional, defaults to user account&apos;s primary currency</td>
      <td style="text-align:left">You may only update this if this transaction was not created from an automatic
        import, i.e. if this transaction is not associated with a plaid_account_id</td>
    </tr>
    <tr>
      <td style="text-align:left">asset_id</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Unique identifier for associated asset (manually-managed account). Asset
          must be associated with the same account.</p>
        <p>You may only update this if this transaction was not created from an automatic
          import, i.e. if this transaction is not associated with a plaid_account_id</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">recurring_id</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Unique identifier for associated recurring expense. Recurring expense
        must be associated with the same account.</td>
    </tr>
    <tr>
      <td style="text-align:left">notes</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Max 350 characters</td>
    </tr>
    <tr>
      <td style="text-align:left">status</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Optional, defaults to <code>uncleared</code>
      </td>
      <td style="text-align:left">Must be either <code>cleared</code> or <code>uncleared</code>. Defaults to <code>uncleared</code>
        <br
        />If recurring_id is provided, the status will automatically be set to <code>recurring</code> or <code>recurring_suggested</code> depending
        on the type of recurring_id</td>
    </tr>
    <tr>
      <td style="text-align:left">external_id</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>User-defined external ID for transaction. Max 75 characters. External
          IDs must be unique within the same asset_id.</p>
        <p>You may only update this if this transaction was not created from an automatic
          import, i.e. if this transaction is not associated with a plaid_account_id</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">split</td>
      <td style="text-align:left">array of Split objects (see below)</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Defines the split of a transaction. You may not split an already-split
        transaction, recurring transaction, or group transaction.</td>
    </tr>
  </tbody>
</table>### Split object

TODO: Check required/optional

<table>
  <thead>
    <tr>
      <th style="text-align:left">Key</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left"></th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">date</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Must be in ISO 8601 format (YYYY-MM-DD)</td>
    </tr>
    <tr>
      <td style="text-align:left">category_id</td>
      <td style="text-align:left">number</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Unique identifier for associated category_id. Category must be associated
        with the same account.</td>
    </tr>
    <tr>
      <td style="text-align:left">notes</td>
      <td style="text-align:left">string</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">amount</td>
      <td style="text-align:left">number | string</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">
        <p>Individual amount of split.</p>
        <p>Note: all amounts must sum up to parent transaction amount.</p>
        <p>Note: currency will inherit from parent transaction.</p>
      </td>
    </tr>
  </tbody>
</table>