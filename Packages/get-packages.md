{{{
  "title": "Get Packages",
  "date": "5-22-2015",
  "author": "Bryan Friedman",
  "attachments": []
}}}

Gets the list of packages that are available in a given account. Calls to this operation must include a token acquired from the authentication endpoint. See the [Login API](../Authentication/login.md) for information on acquiring this token.

### When to Use It

Use this API operation when you need the details of packages that are available in a given account. Packages can be executed on a server using a call to the [Execute Package](../Servers/execute-package.md) method by passing the unique ID and required parameters.

## URL

### Structure

    GET https://api.ctl.io/v2/packages/{accountAlias}

### Example

    GET https://api.ctl.io/v2/packages/ALIAS

## Request

### URI Parameters

| Name | Type | Description | Req. |
| --- | --- | --- | --- |
| AccountAlias | string | Short code for a particular account | Yes |

## Response

The response will be an array containing one entity for each package in the given account.

### Entity Definition

| Name | Type | Description |
| --- | --- | --- |
| id | string | Unique identifier for the package. |
| name | string | The name of the package as defined when it was published. |
| visibility | string | The visibility of the package as defined when it was published. One of the following: `public`, `private`, or `shared`. |
| description | string | Description of the package as defined when it was published. |
| parameters | array | Lists the parameter entities described in the package manifest, if defined. Used to determine what parameters to send when executing the package using the [Execute Package](../Server Actions/execute-package.md) method. |
| supportedOsTypes | array | List of operating systems supported by this package. |

### Parameters Definition

| Name | Type | Description |
| --- | --- | --- |
| variable | string | Variable name of the parameter. |
| name | string | Friendly display name of the parameter. |
| type | string | The parameter type. One of the following: `numeric`, `option`, `password`, `server`, `serverIP`, `string`, or `multiSelect`. |
| defaultValue | string | The default value for this parameter. |
| required | boolean | Whether or not the parameter is required. |
| regex | string | If defined, the regular expression that the parameter value must match. |
| hint | string | If defined, the hint to show with details about what this parameter is. |
| options | array | If parameter type is `option`, this element defines the list of options to select from.  |

### Options Definition

| Name | Type | Description |
| --- | --- | --- |
| name | string | Display name of option to appear in drop-down list. |
| value | string | Value of option to send to package. |


### Examples

#### JSON

    [
      {
        "id": "ce2236dcb96b4df3a3baa762a2d81a0d",
        "name": "Hello World",
        "visibility": "private",
        "description": "My Hello World program.",
        "parameters": [
          {
            "variable": "email",
            "name": "Enter Your Email Address",
            "type": "string",
            "required": true
          }
        ],
        "supportedOSTypes": [
          "redHat6_64Bit",
          "ubuntu12_64Bit"
        ]
      },
      {
        "id": "9d1bdf3ff8224732b1c725e5dc2fd2bc",
        "name": "Install Special Program on Windows",
        "visibility": "public",
        "description": "Installs a very special program on Windows machines.",
        "parameters": [],
        "supportedOSTypes": [
          "windows2008Enterprise_64Bit",
          "windows2008DataCenter_64Bit",
          "windows2012R2DataCenter_64Bit"
        ]
      }
    ]
