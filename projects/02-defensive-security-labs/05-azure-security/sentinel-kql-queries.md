# Microsoft Sentinel KQL Threat Hunting Queries

## 1. Failed Brute-Force & Impossible Travel Detection
```kql
SigninLogs
| where ResultType != 0
| summarize FailedCount = count(), UniqueIPs = dcount(IPAddress), Locations = make_set(Location) by UserPrincipalName, bin(TimeGenerated, 1h)
| where FailedCount > 10 or UniqueIPs > 2
| sort by FailedCount desc
```

## 2. RBAC Elevation Tracking
```kql
AzureActivity
| where OperationNameValue has "Microsoft.Authorization/roleAssignments/write"
| project TimeGenerated, Caller, ResourceGroupName, OperationNameValue, ActivityStatusValue, Properties
| sort by TimeGenerated desc
```
