# Onboarding and Offboarding
## Purpose
This section highlights the Onboarding and Offboarding protocols of the tenant which includes data lifecycle management
## Architecture Overview
Tenant manually onboards and offboards users. Since this is a small scale business, Lifecycle Management in Entra ID Governance is not used unless the business scales up and needs to automate onboarding/offboarding.
## Onboarding checklist
    1. User created in entra; ensure inputs follow naming conventions
    2. Assign department name correctly ** Check dynamic membership rules for employees security group**
    3. Manager assigned
    4. User is Created
    5. Check if MFA enforced **user is automatically assigned to CA policy; Check just in case**
    6. License is automatically assigned through dynamic membership; Check just in case
    7. Temporary password securely stored, and transmitted to employee via email
    8. Documented in ticket system

  ## Offboarding Checklist
    1. Sign-in blocked immediately
    2. Active sessions revoked
    3. Licenses removed
    4. Remove user from all groups; Set department to null
    5. Soft delete account

## Data Lifecycle Management For Offboarding
After device is soft deleted, the data is retained for 30 days in case the data needs to be recovered. After 30 days, the data is permanently deleted. 

