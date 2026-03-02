# Application Deployment (Win 32)
## Purpose
This section documents the protocols used to deploy, manage and update applications via Intune using a staged-rollout method.
Lifecycle governance is the intent and the end result will be controlled deployment with reduced user diruption

## Architecture Overview

Application deployment follows a 2 phase model using entra security groups for staged installation of apps.

### Assignment Strategy
2 security groups made:

1. Pilot for testing

2. Standard group for broad deployment
   
Apps are deployed as:
1. Required (auto-install)
2. Available (company portal)



