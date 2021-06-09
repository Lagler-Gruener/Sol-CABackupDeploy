# Welcome to my CABackup solution.
You can find here the installation process for the whole solution.
The monthley fee for that solution (Microsoft consumption) is aprox 50€

#### Okay let's start, to install the solution deploy the Azure storage account first:

[![Deploy Azure storage account](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FLagler-Gruener%2FSol-CABackupDeploy%2Fmain%2FStorageAccount%2Fdeploystorageaccount.json)

That deployment includes the Azure storage account and the required Azure storage tables
* cabackup
* catranslation
* cabackupconfiguration

### Deployment input:

![Deplyoment](./StorageAccount/images/storagedeployment.png)

### Result:

![Finished](./StorageAccount/images/finisheddeployment.png)

<hr/>

#### Next step is the user assigned managed identity deployment

That deployment step includes the Azure user assigned managed identits, which is important for the whole solution.
Keep in mind, we have to copy the user assigned managed identity 'client id' when the deployment is finished!

[![Deploy Azure storage account](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FLagler-Gruener%2FSol-CABackupDeploy%2Fmain%2FAzureMI%2Fdeploymanagedidentity.json)



<hr/>

#### Next step is the keyvault deployment

[![Deploy Azure storage account](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FLagler-Gruener%2FSol-CABackupDeploy%2Fmain%2FKeyVault%2Fdeploykeyvault.json)

That 