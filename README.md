## Mezuri ARM Templates 

### Shared Resources 
[![Shared Resources](https://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fgithub.com%2Flinl33%2FmezuriAzureTemplate%2Fraw%2Fmaster%2Fshared.json)

### Shared Resources with Disk Encryption Key Vault
[![Shared Resources With Vault](https://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fgithub.com%2Flinl33%2FmezuriAzureTemplate%2Fraw%2Fmaster%2Fshared-withKeyVault.json)

### ODK Sync Resources 
[![ODK Sync Resources](https://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fgithub.com%2Flinl33%2FmezuriAzureTemplate%2Fraw%2Fmaster%2Fsync.json)

### Additional Steps to Enable Disk Encryption 
 - Encrypt disks with this [template provided by Azure](https://github.com/Azure/azure-quickstart-templates/tree/master/201-encrypt-running-linux-vm)
   - `Aad Client ID` and `Aad Client Secret` need to match `Key Vault Service Principal Object Id` entered in the Shared Resources template
   - Choose "All" for `Volume Type`
   - `Key Vault Name/Resource Group` is the Key Vault created by the Shared Resources template 
 - Use `az vm encryption show` or `Get-AzureRmVMDiskEncryptionStatus` to get encryption status