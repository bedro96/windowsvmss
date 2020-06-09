# windows vmss with custom script
Windows Server 2016 vmss created from ARM Template. To deploy, 
```az deployment group create --name vmsstemplate --resource-group vmsscustomscale --template-file template.json --parameters @parameters.json```
