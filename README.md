# Welcome to my CABackup solution.
You can find here the installation process for the whole solution.
The monthley fee for that solution (Microsoft consumption) is aprox 50€

#### Okay let's start, to install the solution deploy the Azure storage account first:

[![Deploy Azure storage account](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FLagler-Gruener%2FSol-CABackupDeploy%2Fmain%2FStorageAccount%2Fdeploystorageaccount.json)

That deployment includes the Azure storage account and the required Azure storage tables
* cabackup
* catranslation
* cabackupconfiguration