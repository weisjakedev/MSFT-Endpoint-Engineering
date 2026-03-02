# Organization of this lab
All Major sections of this lab are listed below. Each of the sections below are divided into subfolders for each policy. Within each subfolder you will find a README.me document with an overview of the architecture and the rationale behind it. You will also find subfolders named EVIDENCE which contain .md files starting with "config" or "validation" followed by the protocol name. .md Files starting with "config" include the step by step configs with screenshots; .md Files starting with "validation" show the step by step validation that the protocol is functional with screenshots.
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

-Onboarding & Offboarding protocols

-Break-Glass Emergency Recovery Account

## Intune Endpoint Architecture

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

## Security & Monitoring

-Administrative and identity events are monitored via sentinel:

-Sign-in log review

-Audit logging

-Privileged elevation tracking


All logs are accounted for and high-risk security threats such as prviiege elevation are traceable within the tenant.
