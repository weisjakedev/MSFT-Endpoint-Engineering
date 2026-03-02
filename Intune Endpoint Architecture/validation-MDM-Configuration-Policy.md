# Validation
Bitlocker keys weren't found in Entra so I had to troublsehoot first:

### Powershell 
```Powershell
#Verify Device trust is established
dsregcmd /status

#Device trust is established
AzureADJoined=yes
AzureADPrt=yes
# Verify TPM protection
manage-bde -protectors -get C: 
# Tpm protection was enabled but recovery password was missing (required in my configuration policy)

# Enable recovery protection
manage-bde -protectors -disable C:
manage-bde -protectors -add C: -Recoverypassword
manage-bde -protectors -enable C:
```
## Device is Now in compliance
<img width="808" height="472" alt="image" src="https://github.com/user-attachments/assets/44411e39-5206-420b-aa70-b4043fd8d700" />
## Check Entra for recovery keys

<img width="1984" height="489" alt="image" src="https://github.com/user-attachments/assets/b007d092-a937-4ad9-b9e3-48c6f2e74708" />

