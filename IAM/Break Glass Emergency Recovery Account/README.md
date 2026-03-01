# Emergency Access Account

## Purpose
This is a designated emergency access account to ensure administrative recovery in the event of Conditional Access misconfiguration or authentication service disruption.

## Scope
Excluded from:
-Conditonal Access
-MFA
-Licensing
## Conditional Access
In the case that an admin is locked out because of a misconfigured CA policy or some other fatal error, this account is avilable.
For configuration reference: https://github.com/weisjakedev/MSFT-Endpoint-Engineering/tree/main/IAM/Conditional%20Access

## Excluded From MFA
In the case that there is a teneant-wide MFA failure, this account is available

<img width="1646" height="1046" alt="image" src="https://github.com/user-attachments/assets/384d8ff2-b1c9-4f0f-b65d-c82b13f67dfb" />

## Extensive Logging Of Sign-in Events
In the case that the break-glas account signs in, a high severity alert is sent to sentinel.
 See: https://github.com/weisjakedev/MSFT-Endpoint-Engineering/blob/main/Security%20%26%20Monitoring/README.md
