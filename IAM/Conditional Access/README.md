# Conditional Access & SSO
## Purpose
This section documents the implementation of Conditional Access to enforce risk-based access control and session security across the tenant.
Policies evaluate user identity and risk signals to determine whether access should be allowed, blocked, or require additional controls such as MFA.
Session controls are applied to ensure authentication is periodically revalidated and that elevated risk conditions trigger reauthentication when necessary.
## Scope 
Included:
1. All standard users (via ALL-EMP-SG)
2. Global admin (via GLOBAL-ADMIN-SG)

Excluded: 
1. Break-glass admin (via BREAK-GLASS-SG;) Break-glass is an emergency acount that is excluded from MFA in the case of a tenant-wide MFA malfunction ** For more reference see https://github.com/weisjakedev/MSFT-Endpoint-Engineering/tree/main/IAM/**Configuration%20Of%20Break-Glass%20Emergency%20Recovery%20Admin**

## Architecture Overview
One baseline policy (CA-Baseline-MFA-All-Users), one high user risk policy (CA-Require-MFA-High-User-Risk-Remediation) , and one high sign in risk policy (CA-Require-MFA-HighSignIn-Risk)

### CA-Baseline-MFA-All-Users
This baseline policy requires all users to use MFA when starting a new session. However, there is a trusted-ip which is excluded from MFA, the company building's subnet; If a user is on the premises of the company and using their ip range they will not be prompted for MFA. In either case, when authenticated a refresh token(PRT) is issued and a user can access all company resources eithout needing to reauthenticate (SSO)
##### A note on trusted ip 
Excluding a trusted-ip on it's own can be risky. Lateral movement can occur and an attacker can escalate their privileges to get more sensitive information. I do not solely exclude a trusted location; I require device compliance policies in intune and require approval from security admin to elevate privileges. To see THOSE configs, please reference https://github.com/weisjakedev/MSFT-Endpoint-Engineering/tree/main/Endpoint%20Management%20Architecture and https://github.com/weisjakedev/MSFT-Endpoint-Engineering/tree/main/Security%20&%20Monitoring

### CA-Require-MFA-High-User-Risk-Remediation
If a user is flagged as high risk by Microsoft's anomaly detection algorithm a user wil be flagged as high risk. In this policy, any device requiring



