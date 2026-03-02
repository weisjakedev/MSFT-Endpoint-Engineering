# Configuration
## Create Policy For Disk Encryption 

<img width="1109" height="340" alt="image" src="https://github.com/user-attachments/assets/a53661e4-62e3-49e9-bb59-077afcb9425b" />


<img width="1237" height="694" alt="image" src="https://github.com/user-attachments/assets/7fc114ec-e95d-4161-8d87-bcfc9bb51a52" />

<img width="721" height="544" alt="image" src="https://github.com/user-attachments/assets/6bc46605-cd86-4557-abdc-0e7d66317bca" />

##       Key Flags that I would like to emphasize due to their importance:
    • Configured bitlocker to require device encryption (main policy)
    • Require bitlocker key to be saved into entra for operating system drives as well as fixed system drives: **Store recovery passwords and keypackages not just the password; Key packages allow for advanced recovery (such as corrupted boot environment)
    • Require TPM because it provides hardware-backed cryptographic protection; It ensures that encryption keys are bound to trusted hardware which protects against offline disk attacks. 
    • Choose minimal AD DS settings because this is used for on-prem deployments, this is a cloud-based AD deployment so this is N/A
    • Choose XTS-AES-256 bit encryption because this is the strongest
