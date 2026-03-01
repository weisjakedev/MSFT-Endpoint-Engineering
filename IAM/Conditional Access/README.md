# Conditional Access
## Purpose
This section documents the implementation of Conditional Access to enforce risk-based access control and session security across the tenant.
Policies evaluate user identity and risk signals to determine whether access should be allowed, blocked, or require additional controls such as MFA.
Session controls are applied to ensure authentication is periodically revalidated and that elevated risk conditions trigger reauthentication when necessary.
## Scope 
Included:
1. All standard users (via ALL-EMP-SG)
2. Global admin (via GLOBAL-ADMIN-SG)

Excluded: 
1. Break-glass Emergency
