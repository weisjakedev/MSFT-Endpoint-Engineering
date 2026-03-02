# Configuration Of Required Win32 App (Notepad++)
## Create 2 security groups for apps
Pilot group and broad deployment

<img width="528" height="409" alt="image" src="https://github.com/user-attachments/assets/f439c349-ff8d-4b10-a3ea-d71e98986be5" />

## Prepare Win 32 app for Intune
```Powershell
PS C:\intuneapps\intunetool> ./intunewinapputil.exe
Please specify the source folder: C:/intuneapps/notepadapp
Please specify the setup file: npp.8.9.2.Installer.x64.exe
Please specify the output folder: C:/intuneapps/output
Do you want to specify the catalog folder (Y/N)?
```
## Add application in Intune
Check documentation of app for install/uninstall commmands

<img width="720" height="590" alt="image" src="https://github.com/user-attachments/assets/bd1d6013-73e2-4d9c-acdc-a34dd1c5fb6a" />

## Set detection rules to correct path
** Most Important **

<img width="1102" height="302" alt="image" src="https://github.com/user-attachments/assets/1e28ae70-7765-42f7-984f-94a223da5579" />

## Assign to pilot group

<img width="1094" height="325" alt="image" src="https://github.com/user-attachments/assets/35336113-910b-483c-8c2f-c877e5ebc104" />



