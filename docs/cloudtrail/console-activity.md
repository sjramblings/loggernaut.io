---
slug: console-activity
title: Console Activity
tags: [cloudtrail, console, activity]
---

Queries events from AWS CloudTrail logs indicating console activity via read-only events. Results are filtered to include only events from users or roles authenticated from the "loggernaut.io" domain.

This query can be useful for security monitoring, auditing, or investigating specific events within your AWS environment, focusing on user activities made by users or roles within a particular organization or domain.

## Search Filter

```sql
fields @timestamp, eventTime, recipientAccountId, eventName, userIdentity.principalId, userIdentity.invokedBy
| filter recipientAccountId = '123456789012'
| filter readOnly = '1'
| filter userIdentity.invokedBy not like /.*.amazonaws.com$/
| filter userIdentity.principalId like /.*@loggernaut.io$/
| sort recipientAccountId desc
```

## Optional Parameters

| Name | Default | Description |
| ------------------------|----------------|------------------|
| recipientAccountId | * | Narrow the search to particular AccountId. Useful when searching Organization CloudTrails in a multi-account environment |
| userIdentity.principalId | * | This regular expression matches principal IDs that end with @loggernaut.io, which is used to filter events specific to users or roles within the "loggernaut.io" domain or organization. These users would likely come from an IDP such as Azure AD. |

## Example Output

## References

- 