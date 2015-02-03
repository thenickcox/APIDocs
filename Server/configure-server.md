{{{
  "title": "Configure Server",
  "date": "5-1-2013",
  "author": "Troy Schneringer",
  "attachments": []
}}}

ConfigureServer
<p>Configures the CPU, Memory, Group and additional storage for a Server.</p>
URL
<pre>REST: https://api.tier3.com/REST/Server/ConfigureServer/&lt;format&gt;<br />SOAP: https://api.tier3.com/SOAP/Server.asmx?op=ConfigureServer</pre> Request
<h3>Attributes</h3>
<table>
  <tbody>
    <tr>
      <td><strong>Name</strong>
      </td>
      <td><strong>Type</strong>
      </td>
      <td><strong>Description</strong>
      </td>
      <td><strong>Required</strong>
      </td>
    </tr>
    <tr>
      <td>AccountAlias</td>
      <td>String</td>
      <td>The alias of the account that owns the server. If not provided it will assume the Account the API user is mapped to. Providing this value gives you the ability to manage servers in your sub accounts.</td>
      <td>No</td>
    </tr>
    <tr>
      <td>Name</td>
      <td>String</td>
      <td>The name of the server. &nbsp;</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>HardwareGroupID</td>
      <td>Int</td>
      <td>The ID of the Hardware Group to add this server to.</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>Cpu</td>
      <td>Int</td>
      <td>The number of processors to configure the server with.Valid values are 1, 2 and 4</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>MemoryGB</td>
      <td>Int</td>
      <td>The number of GB of memory to configure the server with.Valid values are between 1 and 16.</td>
      <td>Yes</td>
    </tr>
    <tr>
      <td>AdditionalStorageGB</td>
      <td>Int</td>
      <td>If greater than 0, the size a new disk to add to the server.</td>
      <td>No</td>
    </tr>
    <tr>
      <td>CustomFields</td>
      <td>Complex</td>
      <td>A list of Custom Fields associated to this server (see below)</td>
      <td>No</td>
    </tr>
  </tbody>
</table>
<h3>CustomField Attributes</h3>
<table>
  <tbody>
    <tr>
      <td><strong>Name</strong>
      </td>
      <td><strong>Type</strong>
      </td>
      <td><strong>Description</strong>
      </td>
    </tr>
    <tr>
      <td>CustomFieldID</td>
      <td>Int</td>
      <td>Identifier that is associated with the Account Custom Field (Call Account/GetCustomFields for a list of all custom fields set at the account level)</td>
    </tr>
    <tr>
      <td>Value</td>
      <td>String</td>
      <td>For Text: Any value;&nbsp;For Option values, call Account/GetCustomFields to see possible values to pass in. Checkbox values should be "true" or "false".
        <br />
        <br />
      </td>
    </tr>
  </tbody>
</table>
<h3>Examples</h3>
<h4>JSON</h4>
<pre>{

  "AccountAlias": "UNK",

  "Name": "WA1T3NWEB01",

  "HardwareGroupID": 1,

  "Cpu": 2,

  "MemoryGB": 4,

  "AdditionalStorageGB": 50,

  "CustomFields":[<br />                { "CustomFieldID": 100,"Value": "A test"},<br />                { "CustomFieldID": 101,"Value": "2"},<br />                { "CustomFieldID": 102,"Value": "true"},]

}</pre>
<h4>XML</h4>
<pre>&lt;ConfigureServerRequest&gt;

    &lt;AccountAlias&gt;UNK&lt;/AccountAlias&gt;

    &lt;Name&gt;WEB&lt;/Name&gt;

    &lt;HardwareGroupID&gt;1&lt;/HardwareGroupID&gt;

    &lt;Cpu&gt;2&lt;/Cpu&gt;

    &lt;MemoryGB&gt;4&lt;/MemoryGB&gt;

    &lt;AdditionalStorageGB&gt;50&lt;/AdditionalStorageGB&gt;

    &lt;CustomFields CustomFieldID="100" Value="Test text" /&gt;

    &lt;CustomFields CustomFieldID="104" Value="2" /&gt;

    &lt;CustomFields CustomFieldID="108" Value="true" /&gt;

&lt;/ConfigureServerRequest&gt;</pre> Response
<h3>Attributes</h3>
<table>
  <tbody>
    <tr>
      <td><strong>Name</strong>
      </td>
      <td><strong>Type</strong>
      </td>
      <td><strong>Description</strong>
      </td>
    </tr>
    <tr>
      <td>Success</td>
      <td>Boolean</td>
      <td>True if the request was successful, otherwise False.</td>
    </tr>
    <tr>
      <td>Message</td>
      <td>String</td>
      <td>A description of the result. The contents of this field does not contain any actionable information, it is purely intended to provide a human readable description of the result.</td>
    </tr>
    <tr>
      <td>StatusCode</td>
      <td>Int</td>
      <td>This value will help to identify any errors which were encountered while processing the request. The value of '0' indicates success, all non-zero StatusCodes indicate an error state.</td>
    </tr>
    <tr>
      <td>RequestID</td>
      <td>Int</td>
      <td>
        <p>The ID of the Queued request.</p>
        <p>Status of the request can be obtained by calling the&nbsp;<a href="http://help.tier3.com/entries/20561586-get-deployment-status">GetDeploymentStatus</a>&nbsp;method.</p>
      </td>
    </tr>
  </tbody>
</table>
<h3>Examples</h3>
<h4>JSON</h4>
<pre>{<br />    "RequestID":1,<br />    "Success":true,<br />    "Message":"Success",<br />    "StatusCode":0<br />}</pre>
<h4>XML</h4>
<pre>&lt;QueuedItemResponse Success="true" Message="Success" StatusCode="0"&gt;<br />&nbsp; &nbsp; &lt;RequestID&gt;1&lt;/RequestID&gt;<br />&lt;/QueuedItemResponse&gt;</pre>
<h3>Status Codes</h3>
<table>
  <tbody>
    <tr>
      <td><strong>Status Code</strong>
      </td>
      <td><strong>Description</strong>
      </td>
    </tr>
    <tr>
      <td>0</td>
      <td>Request was successfully processed</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Unknown Error - An application error occurred processing your request, contact Tier3 support to resolve the issue.</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Invalid Request Format. This value indicates that the XML or JSON requests do not match the expected format.</td>
    </tr>
    <tr>
      <td>5</td>
      <td>
        <p>Resource Not Found. &nbsp;</p>
        <p>A Hardware Group with the specified ID cannot be found.
          <br />- OR -
          <br />A Server with the specified Name cannot be found&nbsp;</p>
      </td>
    </tr>
    <tr>
      <td>6</td>
      <td>
        <p>Invalid Operation. &nbsp;Server must be in an active state.</p>
      </td>
    </tr>
    <tr>
      <td>100</td>
      <td>Authentication Failed - You must logon to the API prior to calling this method.</td>
    </tr>
    <tr>
      <td>500</td>
      <td>Invalid Memory Value.</td>
    </tr>
    <tr>
      <td>501</td>
      <td>Invalid CPU Value.</td>
    </tr>
    <tr>
      <td>541</td>
      <td>Hardware Group ID Required.&nbsp;</td>
    </tr>
    <tr>
      <td>1310</td>
      <td>Name Required.</td>
    </tr>
    <tr>
      <td>1413</td>
      <td>Additional Storage max size exceeded.</td>
    </tr>
  </tbody>
</table>