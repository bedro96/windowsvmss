# windows vmss with custom script
Windows Server 2016 vmss created from ARM Template. To deploy,
1. Create a resource group 
```az group create -n test-vmss-rg -l koreacentral```

2. Deploy ARM template file
```az deployment group create --name vmsstemplate --resource-group test-vmss-rg --template-file template.json --parameters @parameters.json```
