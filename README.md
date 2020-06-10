## Windows vmss with custom script
운영계 배포방법
운영계 배포를 위해서 prod_vmss_template.json, prod_vmss_parameters.json을 준비합니다. 
운영계에서는 기존 vNet이 배포하고자 하는 resource group내에 존재해야만 하며, vmss만을 배포합니다. 
배포에 필요한 정보로 prod_vmss_parameters.json 수정하고 배포 이후에 Load Balancer의 backend로 등록하시면 됩니다. 
``` az deployment group create --name prod_vmss_deploy --resource-group prod-vmss-rg --template-file prod_vmss_template.json --parameters prod_vmss_parameters.json ```

개발계 배포방법
개발계 배포를 위해서는 test_basiclb_vmss_template.json, test_basiclb_vmss_parameters.json을 준비합니다. 개발계에서는 Public Load Balancer와 VMSS을 함께 배포해서 실 환경과 유사한 환경을 제공합니다. 배포에 필요한 정보는 test_basiclb_vmss_parameters.json을 수정하고, 배포하시면 됩니다. 
1.	test-vmss-rg라는 리소스 그룹을 생성을 합니다. 
``` az group create -n test-vmss-rg -l koreacentral ```
2.	다음 명령어를 실행해서 신규 생성된 리소스 그룹에 lb와 vmss를 배포합니다.
``` az deployment group create --name test_vmss_deploy --resource-group test-vmss-rg --template-file test_basiclb_vmss_template.json --parameters test_basiclb_vmss_parameters.json ```
