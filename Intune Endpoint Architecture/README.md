# Intune Endpoint Architecture

## Purpose

This section documents the implementation of a zero-touch endpoint management architecture designed to establish device trust, enforce compliance standards, and integrate endpoint posture with conditional access

The objective is to ensure that only securely provisioned and policy-compliant devices are permitted to access corporate resources.

## Architecture overview

### Zero-Touch Provisioning (Autopilot)

Devices are provisioned using a conceptual Windows Autopilot deployment model to eliminate manual device configuration, enforce standard configuration at first sign-in, automatically enroll devices into Intune and Apply security baselines upon enrollment

### Device Compliance Enforcement
Device compliance policies require:

-BitLocker encryption enabled

-TPM present and healthy

-Secure Boot enabled

-Recovery key escrowed to Entra ID

-Microsoft Defender Antivirus enabled

Devices failing compliance are blocked from accessing corporate resources via Conditional Access. see: https://github.com/weisjakedev/MSFT-Endpoint-Engineering/blob/main/IAM/Conditional%20Access/Evidence/config-CA-Require-MDM%20Enrollment%26Compliance.md

### Security Baseline & Endpoint Hardening
Microsoft Defender security baseline is deployed to enforce recommended microsoft hardening settings, configure ASR rules and standardize endpoint security posture

All enrolled devices are onboarded into Microsoft Defender for Endpoint for continuous threat monitoring

### Conditional access 
Only devices marked as MDM compliant in Intune are permitted access to microsoft 365 resources.

