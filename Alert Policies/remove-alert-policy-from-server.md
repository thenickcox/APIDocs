{{{
  "title": "Remove Alert Policy from Server",
  "date": "05-25-2015",
  "author": "Bryan Friedman",
  "attachments": []
}}}

Removes the specified alert policy from a given server. Calls to this operation must include a token acquired from the authentication endpoint. See the [Login API](../Authentication/login.md) for information on acquiring this token.

### When to Use It

Use this API operation when you want to remove a particular alert policy from a server. To see which alert policies are currently applied to the server, use the [Get Server](../Servers/get-server.md) method and look in the `alertPolicies` section of the server `details`.

## URL

### Structure

    DELETE https://api.ctl.io/v2/servers/{accountAlias}/{serverId}/alertPolicies/{policyId}

### Example

    DELETE https://api.ctl.io/v2/servers/ALIAS/WA1ALIASSERV0101/alertPolicies/21fa6f1239887d8fa33eca9876d5b807

## Request

### URI Parameters

| Name | Type | Description | Req. |
| --- | --- | --- | --- |
| AccountAlias | string | Short code for a particular account | Yes |
| ServerId | string | ID of the server. Retrieved from query to containing group, or by looking at the URL when viewing a server in the Control Portal. | Yes |
| PolicyId | string | ID of the alert policy to remove. | Yes |

## Response

The response will not contain JSON content, but should return the HTTP `204 No Content` response upon deletion of the policy.
