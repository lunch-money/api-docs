# Plaid Accounts object

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Attribute</b>
      </th>
      <th style="text-align:left"></th>
      <th style="text-align:left"><b>Type</b>
      </th>
      <th style="text-align:left"></th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>id</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">number</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Unique identifier of Plaid account</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>date_linked</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Date account was first linked in ISO 8601 extended format</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>name</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Name of the account. Can be overridden by the user. Field is originally
        set by Plaid</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>type</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Primary type of account. Typically one of:</p>
        <ul>
          <li>credit</li>
          <li>depository</li>
          <li>brokerage</li>
          <li>cash</li>
          <li>loan</li>
          <li>Investment</li>
        </ul>
        <p>This field is set by Plaid and cannot be altered</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>subtype</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string,</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Optional subtype name of account. This field is set by Plaid and cannot
        be altered</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>mask</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Mask (last 3 to 4 digits of account) of account. This field is set by
        Plaid and cannot be altered</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>institution_name</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Name of institution associated with account. This field is set by Plaid
        and cannot be altered</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>status</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Denotes the current status of the account within Lunch Money. Must be
          one of:</p>
        <ul>
          <li><code>active</code>: Account is active and in good state</li>
          <li><code>inactive</code>: Account marked inactive from user. No transactions
            fetched or balance update for this account.</li>
          <li><code>relink</code>: Account needs to be relinked with Plaid.</li>
          <li><code>syncing</code>: Account is awaiting first import of transactions</li>
          <li><code>error</code>: Account is in error with Plaid</li>
          <li><code>not found</code>: Account is in error with Plaid</li>
          <li><code>not supported</code>: Account is in error with Plaid</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>last_import</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Date of last imported transaction in ISO 8601 extended format (not necessarily
        date of last attempted import)</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>balance</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Current balance of the account in numeric format to 4 decimal places.
        This field is set by Plaid and cannot be altered</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>currency</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Currency of account balance in ISO 4217 format. This field is set by Plaid and cannot be
        altered</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>balance_last_update</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Date balance was last updated in ISO 8601 extended format. This field
        is set by Plaid and cannot be altered</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>limit</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">number</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Optional credit limit of the account. This field is set by Plaid and cannot be
        altered</td>
    </tr>
  </tbody>
</table>
