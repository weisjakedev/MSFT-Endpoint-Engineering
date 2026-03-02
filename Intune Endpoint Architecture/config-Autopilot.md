# Conceptual Configuration
I am limited in my lab environment for autopilot configs. So I will explain conceptually how I would deploy autopilot.

## Register Device With Hash
Vendor would upload hash in zero-touch deployment or IT department would use powershell to get hash( My case).

<img width="1256" height="509" alt="image" src="https://github.com/user-attachments/assets/6a95db53-f8e3-41eb-a143-5a7556cfc991" />
<img width="1277" height="669" alt="image" src="https://github.com/user-attachments/assets/4fc2f1da-9d3a-421e-b21c-83030c33444a" />

## Create Autopilot Deployment Profile
<img width="674" height="635" alt="image" src="https://github.com/user-attachments/assets/78ed91df-afc7-4323-99f6-dc1b4f521271" />

## Assign to all devices

<img width="1015" height="640" alt="image" src="https://github.com/user-attachments/assets/21459cbf-d3ee-42a4-8c69-c57c087c41d9" />

##  Device provisioning workflow:
    1. Vendor registers device with autopilot service.
    2. Device ships directly to employee.
    3. Employee powers on.
    4. Connects to Wi-Fi.
    5. Signs in with Entra credentials.
    6. Device:
    • Joins entra
    • Enrolls in intune
    • Applies compliance policy
    • Deploys required apps
    • Applies security baseline
    • ESP completes.
    • User lands on secured desktop.
