# Conditional Access & SSO
## Purpose
This section documents the conditional access policy implemented to enforce adaptive authentication and risk-based access control across the tenant.
Policies evaluate identity signals such as user risk, sign-in risk, device compliance, and session context to determine whether access should be allowed, blocked, or require additional controls such as multi-factor authentication (MFA) or credential reset.

Session controls ensure authentication is periodically revalidated and that elevated risk conditions trigger reauthentication as required.
## Scope 
Included:
1. All standard users (via ALL-EMP-SG)
2. Global admin (via GLOBAL-ADMIN-SG)

Excluded: 
1. Break-glass admin (via BREAK-GLASS-SG;) Break-glass is an emergency acount that is excluded from MFA in the case of a tenant-wide MFA malfunction ** For more reference see https://github.com/weisjakedev/MSFT-Endpoint-Engineering/tree/main/IAM/**Configuration%20Of%20Break-Glass%20Emergency%20Recovery%20Admin**

## Architecture Overview
The Conditional Access model consists of 4 primary policies:
1.CA-Baseline-MFA-All-Users
2.CA-Require-Remediation-High-User-Risk
3.CA-Require-MFA-High-Sign-In-Risk
4.CA-Require-MDM Enrollment&Compliance

### CA-Baseline-MFA-All-Users
This policy enforces MFA for all users when initiating a new authentication session.
A trusted network location representing the corporate subnet is excluded from MFA enforcement. When authentication originates from this trusted IP range, MFA is not required.
Upon successful authentication, access and refresh tokens are issued. On Entra-joined devices, a Primary Refresh Token (PRT) enables seamless single sign-on (SSO) across Microsoft 365 services for the duration of the session.
##### Security Considerations: Trusted Network Exclusion
Excluding trusted network locations from MFA introduces risk, particularly in scenarios involving lateral movement or compromised internal devices. To mitigate this, additional controls are implemented:
1.Device compliance enforcement via Intune
 https://github.com/weisjakedev/MSFT-Endpoint-Engineering/tree/main/Endpoint%20Management%20Architecture
2.Privileged role elevation approval through PIM
 https://github.com/weisjakedev/MSFT-Endpoint-Engineering/tree/main/Security%20&%20Monitoring
3.Privilege elevation monitoring through Defender alert queries
This layered approach reduces reliance on perimeter-based trust. and

### CA-Require-MFA-High-User-Risk-Remediation
This policy enforces credential remediation when Microsoft Identity Protection classifies a user as High risk.

Grant Control:

Require password change

This ensures that potentially compromised credentials are rotated before access is restored. Upon password reset, existing refresh tokens are invalidated and the user must reauthenticate.
### CA-Require-MFA-High-Sign-In-Risk
This policy enforces MFA when a sign-in attempt is evaluated as High risk. Unlike user risk, sign-in risk is evaluated per authentication event. If a risky authentication attempt is detected, MFA is required even if the user has an existing session. This ensures adaptive authentication based on real-time threat signals.
### CA-Require-MDM Enrollment&Compliance
This policy requires devices to be marked as compliant by Intune before access to cloud applications is granted.

Grant Control:

Require device to be marked as compliant

Device compliance is evaluated through Intune compliance policies, which enforce security standards such as bitlocker encryption and defender antivirus. 


