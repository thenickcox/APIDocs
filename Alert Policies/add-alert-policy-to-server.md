{{{
  "title": "Add Alert Policy to Server",
  "date": "05-25-2015",
  "author": "Bryan Friedman",
  "attachments": []
}}}

Adds an alert policy to a specified server. Calls to this operation must include a token acquired from the authentication endpoint. See the [Login API](../Authentication/login.md) for information on acquiring this token.

### When to Use It

Use this API operation when you want to add an alert policy to a server.

## URL

### Structure

    POST https://api.ctl.io/v2/servers/{accountAlias}/{serverId}/alertPolicies

### Example

    POST https://api.ctl.io/v2/servers/ALIAS/WA1ALIASSERV0101/alertPolicies

## Request

### URI Parameters

| Name | Type | Description | Req. |
| --- | --- | --- | --- |
| AccountAlias | string | Short code for a particular account | Yes |
| ServerId | string | ID of the server. Retrieved from query to containing group, or by looking at the URL when viewing a server in the Control Portal. | Yes |

### Content Properties

| Name | Type | Description | Req. |
| --- | --- | --- | --- |
| id | string | The unique identifier of the alert policy to apply to the server. Can be retrieved by calling [Get Alert Policies](../Alert Policies/get-alert-policies.md). | Yes |

### Examples

#### JSON

    {
      "id": "21fa6f1239887d8fa33eca9876d5b807"
    }

## Response

### Entity Definition

| Name |Type | Value | Description |
| --- | --- | --- | --- |
| id | string | ID of the alert policy. |
| links | array | Collection of [entity links](../Getting Started/api-v20-links-framework.md) that point to resources related to this policy. |

### Examples

#### JSON

    {
      "id": "21fa6f1239887d8fa33eca9876d5b807",
      "links": [
        {
          "rel": "self",
          "href": "/v2/servers/ALIAS/WA1ALIASSERV0101/alertPolicies/21fa6f1239887d8fa33eca9876d5b807",
          "verbs": [
            "DELETE"
          ]
        }
      ]
    }
