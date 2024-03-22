---
slug: user-logins
title: User Logins
tags: [cloudtrail, user, login]
---

Extracts console login events from AWS CloudTrail logs.

This query can be useful for auditing and monitoring console access within your AWS environment. It provides a chronological view of console login activities, allowing you to quickly identify recent login events and the associated usernames.

## Search Filter

```sql
fields @timestamp, eventName, userIdentity.userName
    | filter eventName like /(?i)ConsoleLogin/
    | sort @timestamp desc
```

## Optional Parameters

None

## Example Output

## References

- 