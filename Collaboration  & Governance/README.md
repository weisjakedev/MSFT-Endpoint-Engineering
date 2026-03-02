# Colaboration & Governance
## Purpose
This section documents the collaboration architecture implemented within the tenant to provide secure, organized, and scalable communication channels for employees.
## Architecture overview
Collaboration environment is built using a SharePoint hub-and-spoke model integrated with Teams collaboration spaces.
Hub site was configured in SharePoint to serve as the central navigation and governance point for organizational collaboration resources. Departmental collaboration sites are associated with the hub to provide structured access to team-specific resources.

Microsoft Teams is used as the primary communication platform, with each department represented by a dedicated Teams workspace.

## Access & Permission Governance
Access control is managed using Microsoft 365 group-based membership

-Team owners manage membership lifecycle

-Users are assigned based on department role

-Least-privilege access principles are enforced

## Information Segmentation
Instead of breaking permission inheritance (Sharepoint-native design,) sensitive business communications are protected using private Teams channels.
