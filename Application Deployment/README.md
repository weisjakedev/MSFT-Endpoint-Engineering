# Application Deployment (Win 32)
## Purpose
This section documents the packaging, deployment, lifecycle management, and staged rollout of Win32 applications using Intune.

## Architecture Overview
Win32 applications are packaged as .intunewin files and deployed using a ring-based security group model.

1. Application packaged using Win32 content prep tool

2. Uploaded to Intune

3. Install/Uninstall commands defined

4. Detection rules configured

5. Assigned to staged Entra security groups


### Assignment Strategy
2 security groups made:

1. Pilot for testing

2. Standard group for broad deployment
   
Apps are deployed as:
1. Required (auto-install)
   or
2. Available (company portal)



