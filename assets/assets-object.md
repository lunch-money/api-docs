# Assets Object

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
      <td style="text-align:left">Unique identifier for asset</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>type_name</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Primary type of the account. Must be one of:</p>
        <ul>
          <li>employee compensation</li>
          <li>cash</li>
          <li>vehicle</li>
          <li>loan</li>
          <li>cryptocurrency</li>
          <li>investment</li>
          <li>other</li>
          <li>credit</li>
          <li>real estate</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>subtype_name</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Optional account subtype. Examples include:</p>
        <ul>
          <li>retirement</li>
          <li>checking</li>
          <li>savings</li>
          <li>prepaid credit card</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>name</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Name of the asset</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>balance</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Current balance of the account in numeric format to 4 decimal places</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>balance_as_of</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Date/time the balance was last updated in ISO 8601 extended format</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>currency</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Three-letter lowercase currency code of the balance</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>institution_name</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Name of institution holding the account</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>created_at</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">string</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Date/time the asset was created in ISO 8601 extended format</td>
    </tr>
  </tbody>
</table>