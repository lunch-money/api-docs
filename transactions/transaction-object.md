# Transaction Object

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
| id | number | Unique identifier for tag  |
| name | string | User-facing name of tagGet single transaction |

