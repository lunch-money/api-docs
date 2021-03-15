# Recurring Expenses object

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
      <td style="text-align:left">Unique identifier for recurring expense</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>start_date</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Denotes when recurring expense starts occurring in ISO 8601 format. If
        null, then this recurring expense will show up for all time before end_date</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>end_date</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Denotes when recurring expense stops occurring in ISO 8601 format. If
        null, then this recurring expense has no set end date and will show up
        for all months after start_date</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>cadence</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>One of:</p>
        <ul>
          <li><code>monthly</code>
          </li>
          <li><code>twice a month</code>
          </li>
          <li><code>once a week</code>
          </li>
          <li><code>every 2 months</code>
          </li>
          <li><code>every 3 months</code>
          </li>
          <li><code>every 4 months</code>
          </li>
          <li><code>twice a year</code>
          </li>
          <li><code>yearly</code>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>payee</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Payee of the recurring expense</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>amount</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">number</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Amount of the recurring expense in numeric format to 4 decimal places</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>currency</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Three-letter lowercase currency code for the recurring expense in ISO 4217 format</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>description</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">If any, represents the user-entered description of the recurring expense</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>billing_date</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Expected billing date for this recurring expense for this month in ISO
        8601 format</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>type</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>This can be one of two values:</p>
        <ul>
          <li><code>cleared</code>: The recurring expense has been reviewed by the user</li>
          <li><code>suggested</code>: The recurring expense is suggested by the system;
            the user has yet to review/clear it</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>original_name</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">If any, represents the original name of the recurring expense as denoted
        by the transaction that triggered its creation</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>source</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>This can be one of three values:</p>
        <ul>
          <li><code>manual</code>: User created this recurring expense manually from
            the Recurring Expenses page</li>
          <li><code>transaction</code>: User created this by converting a transaction
            from the Transactions page</li>
          <li><code>system</code>: Recurring expense was created by the system on transaction
            import</li>
        </ul>
        <p>Some older recurring expenses may not have a source.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>plaid_account_id</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">number</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">If any, denotes the plaid account associated with the creation of this
        recurring expense (see <a href="../plaid-accounts/plaid-accounts-object.md">Plaid Accounts</a>)</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>asset_id</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">number</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">If any, denotes the manually-managed account (i.e. asset) associated with
        the creation of this recurring expense (see <a href="../assets/assets-object.md">Assets</a>)</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>transaction_id</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">number</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">If any, denotes the unique identifier for the associated transaction matching
        this recurring expense for the current time period</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>category_id</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">number</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">If any, denotes the unique identifier for the associated category to this
        recurring expense</td>
    </tr>
  </tbody>
</table>