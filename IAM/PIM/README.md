# Priveleged Identity Management

## Purpose

This section documents the implementation of Privileged Identity Management to enforce least-privilege administrative access and control the lifecycle of privileged role assignments.
Administrative roles are assigned as eligible rather than permanent, requiring justification, approval, and time-bound activation. Access-reviews are done routinely and all privilege elevations are logged and integrated with the organization’s monitoring and incident management workflow.

## Control Objective
PIM is implemented to eliminate permanent high-privilege assignments and enforce time-bound/approved access.

## Role Assignment Model
1. All administrative roles are assigned as eligible

2. No permanent Global Administrators (except break-glass)

3. Activation duration: 1–4 hours

4. Justification required

5.  Privilege elevation approved by security admin

## Activation workflow
User requests privileged role --> Provides Justification --> Sets time-frame needed --> Request sent to Security Admin
Security Admin approves (or denies) --> User is assigned privileged role --> Activation logged to Entra audit logs

## Monitoring & detection
PIM audit logs forwarded to Log Analytics

Scheduled KQL query detects: Global Admin activation, sentinel creates incident, SOC reviews event
See config here: https://github.com/weisjakedev/MSFT-Endpoint-Engineering/blob/main/Security%20%26%20Monitoring/Evidence/config-Privileged-Role-Elevation-Detection.md

# Access reviews





