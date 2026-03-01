# Security & Monitoring

## Purpose
This section documents the security monitoring architecture used to detect and generate alerts for high-risk identity and privileged access activities within the tenant.

Identity and administrative logs are centralized into a Log Analytics workspace and integrated with Microsoft Sentinel to enable real-time detection, incident creation, and audit review by security administrators.

## Architecture Overview
Security telemetry from Microsoft Entra ID is forwarded to an Azure Log Analytics workspace via diagnostic settings in entra.

Microsoft Sentinel is connected to the workspace and uses scheduled KQL queries to detect high-risk events and generate security incidents.

Detection rules are implemented for:

1. Privileged role activation events (PIM elevation)

2. Break-glass emergency account sign-in

This architecture ensures centralized logging, alerting, and investigation for threats.

## Privileged Role Elevation Detection

Privileged role activation events are logged through Entra audit logs and forwarded to Azure Monitor.

A scheduled KQL query identifies role activation events where Global admin role is successfully activated and projects information such as the intitting user for entity mapping.

When detected, Microsoft Sentinel generates a security incident for SOC review.

This ensures all privileged access events are auditable and monitored in near real-time.

## Break-glass Emergency Recovery Account Sign-in
Break-glass sign ins are logged through Entra sign-in logs and forwarded to Azure Monitor.
A scheduled KQL query identifies events where sign in with break-glass account are successful.

When detected, Sentiel generates security incident for SOC review.
