{{{
  "title": "Server Links",
  "date": "03-27-2015",
  "author": "Bryan Friedman",
  "attachments": [],
  "sticky": "true"
}}}

### Overview

The following link definitions are related to the servers resource. They may be returned when making a call to [Get Server](../Servers/get-server.md) or other server-related resources.

### Server Link Definitions

| Relation (rel) | Description | Verbs |
| --- | --- | --- |
| alertPolicyMap | Retrieve or modify the given alert policy for the given server. | [DELETE](../Alert Policies/remove-alert-policy-from-server.md) |
| alertPolicyMappings | Retrieve or modify the list of alert policies for the given server. | [POST](../Alert Policies/add-alert-policy-to-server.md) |
| antiAffinityPolicyMapping | Retrieve or modify the anti-affinity policy for the given server. | [GET](../Anti-Affinity Policies/view-anti-affinity-policy-on-server.md) / [PUT](../Anti-Affinity Policies/set-anti-affinity-policy-on-server.md) / [DELETE](../Anti-Affinity Policies/remove-anti-affinity-policy-from-server.md) |
| billing | Retrieve billing information for the given server. | GET |
| capabilities | Retrieve the supported capabilities listing for the given server. | GET |
| cpuAutoscalePolicyMapping | Retrieve or modify the vertical autoscale policy for the given server. | [GET](../Autoscale Policies/view-vertical-autoscale-policy-on-server.md) / [PUT](../Autoscale Policies/set-vertical-autoscale-policy-on-server.md) / [DELETE](../Autoscale Policies/remove-vertical-autoscale-policy-from-server.md) |
| createServer | Create a server. | [POST](../Servers/create-server.md) |
| credentials | Retrieve credentials for the given server. | [GET](../Servers/get-server-credentials.md)
| publicIPAddress | Retrieve or modify a public IP address of the specific server. | [GET](../Public IP/get-public-ip-address.md) / [DELETE](../Public IP/remove-public-ip-address.md) / [PUT](../Public IP/update-public-ip-address.md) |
| publicIPAddresses | Add a public IP address for the given server. | [POST](../Public IP/add-public-ip-address.md) |
| scheduledActivities | Retrieve the list of scheduled activities for the given server. | GET |

### Server Snapshot Definitions

| Relation (rel) | Description | Verbs |
| --- | --- | --- |
| delete | Delete the snapshot for the given server. | DELETE |
| restore | Restore the snapshot for the given server. | POST |
