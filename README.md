## Purpose

Tenant was designed to simulate a Microsoft 365 environment focused on endpoint management, identity governance, and secure collaboration.

The objective was to implement scalable user management, automated device provisioning, controlled privilege assignment, and a structured collaboration architecture.

## IAM

Identity Access Management implemented with:

-Department-based security groups

-Dynamic membership rules

-Role-Based Access Control

-Privileged Identity Management for administrative roles

-Conditional Access policies enforcing MFA and device compliance

-All administrative privileges are assigned as eligible and require approval for elevation.

## Endpoint Management Architecture

-Devices are managed using:

-Windows Autopilot for zero-touch provisioning

-Microsoft Intune for MDM enforcement

-Compliance policies requiring encryption and security baselines

-Conditional Access integration requiring compliant devices for resource access

-All corporate devices must meet compliance standards prior to accessing Microsoft 365 resources.

## Application Deployment/Management

-Application lifecycle is managed via Intune using:

-Required app deployments for business-critical software

-Optional applications via Company Portal

-Staged update rings for patch validation

-Controlled rollout strategy to minimize user disruption

## Collaboration & Governance

-Collaboration architecture includes:

-Microsoft Teams governance structure

-SharePoint hub-and-spoke design

-Group-based permission assignment

-Department-level access segmentation

-Sensitive communications are restricted through RBAC and site-level permission controls.

## Monitoring & Administrative Controls

-Administrative and identity events are monitored through:

-Sign-in log review

-Audit logging

-Privileged elevation tracking

-Policy change tracking

All logs are accounted for and high-risk security threats such as prviiege elevation are traceable within the tenant.
