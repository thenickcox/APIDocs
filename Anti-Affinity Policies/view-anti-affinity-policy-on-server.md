{{{
  "title": "View Anti-Affinity Policy on Server",
  "date": "05-25-2015",
  "author": "Bryan Friedman",
  "attachments": []
}}}

Gets the anti-affinity policy of a given server if it exists. Calls to this operation must include a token acquired from the authentication endpoint. See the [Login API](../Authentication/login.md) for information on acquiring this token.

### When to Use It

Use this API operation when you want to get the anti-affinity policy of a given server.

## URL

### Structure

    GET https://api.ctl.io/v2/servers/{accountAlias}/{serverId}/antiAffinityPolicy

### Example

    GET https://api.ctl.io/v2/servers/ALIAS/WA1ALIASSERV0101/antiAffinityPolicy

## Request

### URI Parameters

| Name | Type | Description | Req. |
| --- | --- | --- | --- |
| AccountAlias | string | Short code for a particular account | Yes |
| ServerId | string | ID of the server. Retrieved from query to containing group, or by looking at the URL when viewing a server in the Control Portal. | Yes |

## Response

### Entity Definition

| Name |Type | Value | Description |
| --- | --- | --- | --- |
| id | string | ID of the anti-affinity policy. |
| links | array | Collection of [entity links](../Getting Started/api-v20-links-framework.md) that point to resources related to this policy. |

### Examples

#### JSON

    {
      "id": "21fa6f1239887d8fa33eca7105d5b605",
      "links": [
        {
          "rel": "self",
          "href": "/v2/servers/ALIAS/WA1ALIASSERV0101/antiAffinityPolicy"
        },
        {
          "rel": "server",
          "href": "/v2/servers/ALIAS/WA1ALIASSERV0101",
          "id": "WA1ALIASSERV0101"
        },
        {
          "rel": "antiAffinityPolicy",
          "href": "/v2/antiAffinityPolicies/ALIAS/21fa6f1239887d8fa33eca7105d5b605",
          "id": "21fa6f1239887d8fa33eca7105d5b605"
        }
      ]
    }
