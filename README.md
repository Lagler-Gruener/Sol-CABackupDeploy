# Welcome to my CABackup solution.
You can find here the installation process for the whole solution.
The monthley fee for that solution (Microsoft consumption) is aprox 50€

<hr/>

#### 1. Okay let's start, to install the solution deploy the Azure storage account first:

That deployment includes the Azure storage account and the required Azure storage tables
* cabackup
* catranslation
* cabackupconfiguration

[![Deploy Azure storage account](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FLagler-Gruener%2FSol-CABackupDeploy%2Fmain%2FStorageAccount%2Fdeploystorageaccount.json)

> #### Deployment input:
> <b style='color:red'>!IMPORTANT!</b> please select an existing resourcegroup or define a new one!

![Deplyoment](./StorageAccount/images/storagedeployment.png)

> #### Result:

![Finished](./StorageAccount/images/finisheddeployment.png)

<hr/>

#### 2. Next step is the user assigned managed identity deployment

That deployment step includes the Azure user assigned managed identits deployment, which is important for the whole solution.
Keep in mind, we have to copy the user assigned managed identity 'client id' when the deployment is finished!

[![Deploy Azure storage account](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FLagler-Gruener%2FSol-CABackupDeploy%2Fmain%2FAzureMI%2Fdeploymanagedidentity.json)

> #### Deployment input:
> <b style='color:red'>!IMPORTANT!</b> please select the resource group created bevor

![Deplyoment](./AzureMI/images/deploymanagedidentity.png)

> #### Result:

![Deplyoment](./AzureMI/images/finisheddeployment.png)

> #### <b style='color:orange'>Now an important part!</b>
> Please copy the output from the deployment, we need that information in the next steps!

![Deplyoment](./AzureMI/images/getmiidstep1.png)

Than:

![Deplyoment](./AzureMI/images/getmiidstep2.png)




<hr/>

#### 3. Now we can deploy the keyvault resource

That deployment step includes the Azure keyvault deployment, which is important for the Web Application.

[![Deploy Azure storage account](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FLagler-Gruener%2FSol-CABackupDeploy%2Fmain%2FKeyVault%2Fdeploykeyvault.json)

> #### Deployment input:
> <b style='color:red'>!IMPORTANT!</b> <br/> 
> * Please select the resource group created bevor
> * Add the object id from the user assigned managed identity
> * Add the Azure storage account connection string

![Deplyoment](./KeyVault/images/keyvaultdeployment.png)

> You can find the Storageconnection string, when you open the deployed storage account and select the following:

![Deplyoment](./KeyVault/images/selectstroageaccountconstring.png)

> #### Result:

![Deplyoment](./KeyVault/images/finisheddeployment.png)

#### 4. Now we can deploy the Azure logic apps including the connectors

That deployment step includes the Azure logicapp and connectors deployment, which represent the basic infrastructure.

[![Deploy Azure storage account](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FLagler-Gruener%2FSol-CABackupDeploy%2Fmain%2FLogicApp%2Fdeploylogicapps.json)