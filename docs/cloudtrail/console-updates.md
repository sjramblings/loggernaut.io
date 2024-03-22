---
slug: console-updates
title: Console Updates
tags: [cloudtrail, console, updates]
---

Queries events from AWS CloudTrail logs, excluding read-only events, specific event names (like console logins, queries, and case management), and events invoked by AWS services.

Results are filtered to include only events from users or roles authenticated from the "loggernaut.io" domain.

This query can be useful for security monitoring, auditing, or investigating specific events within your AWS environment, focusing on user activities and changes made by users or roles within a particular organization or domain.

## Search Filter

```sql
fields @timestamp, eventTime, recipientAccountId, eventName, userIdentity.principalId, userIdentity.invokedBy
| filter recipientAccountId = '123456789012'
| filter readOnly = '0'
| filter eventName not like /(?i)(ConsoleLogin|GetSigninToken|StartQuery|StopQuery|StartLiveTail|StopLiveTail|AddAttachmentsToSet|AddCommunicationToCase|CreateCase|ResolveCase|5dd)/
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