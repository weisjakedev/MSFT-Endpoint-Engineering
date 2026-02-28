# Tenant Architecture
## Purpose
This section documents the identity design of the tenant, including department segmentation, group governance, dynamic membership rules, and automated license assignment. The objective is to create a scalable and auditable identity structure that supports role-based access control (RBAC) and minimizes manual administrative overhead.
## Architecture overview
Identity model is structured around department-based security groups and dynamic membership rules to ensure consistent access control
## Department-based Security Groups
Security groups are created for each business department to enforce RBAC principles and reduce direct user-level permission assignments.
### Naming convention
Groups follow standardized naming format;
Examples: EXEC-SG, FIN-SG, HR-SG
Naming convention improves clarity and administrative consistency
## Dynamic Membership Rules
Dynamic membership used to automate user to group assignment based upon the "DEPARTMENT" attribute in Entra.
### Rule Logic Example
Department-based groups use attribute-based rules:
(Department equals "Executive")
#### Administrative exceptions
Admin and break-glass(emergency admin account) are excluded from dynamic group memberhsip. They use static membership to prevent unintended privilege propogation

