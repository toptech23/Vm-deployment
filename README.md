# Vm-deployment
resourcegroup="Task"
location="WestUS"
az group create --name Task --location WestUS
{
  "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task",
  "location": "westus",
  "managedBy": null,
  "name": "Task",
  "properties": {
    "provisioningState": "Succeeded"
  },
  "tags": null,
  "type": "Microsoft.Resources/resourceGroups"
}
az vm create --resource-group Task --name myVM01 --image Ubuntu2204 --public-ip-sku standard --admin-username techguru --admin-password Temitope1234 --size standard_DS1_V2
{
  "fqdns": "",
  "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task/providers/Microsoft.Compute/virtualMachines/myVM01",
  "location": "westus",
  "macAddress": "60-45-BD-00-46-F0",
  "powerState": "VM running",
  "privateIpAddress": "10.0.0.4",
  "publicIpAddress": "137.135.30.93",
  "resourceGroup": "Task",
  "zones": ""
  
az group export --name Task2 --resource-ids '*' > template.json
az deployment group create --resource-group Task2 --template-file template.json
Please provide string value for 'networkInterfaces_myVM01VMNic_name' (? for help): myVM01VMNic
Please provide string value for 'networkInterfaces_myVM2VMNic_name' (? for help): myVM2VMNic
Please provide string value for 'networkSecurityGroups_myVM01NSG_name' (? for help): myVM01NSG
Please provide string value for 'networkSecurityGroups_myVM2NSG_name' (? for help): myVM2NSG
Please provide string value for 'publicIPAddresses_myVM01PublicIP_name' (? for help): myVM01PublicIP
Please provide string value for 'publicIPAddresses_myVM2PublicIP_name' (? for help): myVM2VNET
Please provide string value for 'virtualMachines_myVM2_name' (? for help): myVM2
Please provide string value for 'virtualNetworks_myVM01VNET_name' (? for help): myVM01VNET
Please provide string value for 'virtualNetworks_myVM2VNET_name' (? for help): myVM2VNET
{
  "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Resources/deployments/template",
  "location": null,
  "name": "template",
  "properties": {
    "correlationId": "097fb306-b5e9-47f4-869f-85410dc084bb",
    "debugSetting": null,
    "dependencies": [
      {
        "dependsOn": [
          {
            "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/networkInterfaces/myVM2VMNic",
            "resourceGroup": "Task2",
            "resourceName": "myVM2VMNic",
            "resourceType": "Microsoft.Network/networkInterfaces"
          }
        ],
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Compute/virtualMachines/myVM2",
        "resourceGroup": "Task2",
        "resourceName": "myVM2",
        "resourceType": "Microsoft.Compute/virtualMachines"
      },
      {
        "dependsOn": [
          {
            "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/networkSecurityGroups/myVM01NSG",
            "resourceGroup": "Task2",
            "resourceName": "myVM01NSG",
            "resourceType": "Microsoft.Network/networkSecurityGroups"
          }
        ],
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/networkSecurityGroups/myVM01NSG/securityRules/default-allow-ssh",
        "resourceGroup": "Task2",
        "resourceName": "myVM01NSG/default-allow-ssh",
        "resourceType": "Microsoft.Network/networkSecurityGroups/securityRules"
      },
      {
        "dependsOn": [
          {
            "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/networkSecurityGroups/myVM2NSG",
            "resourceGroup": "Task2",
            "resourceName": "myVM2NSG",
            "resourceType": "Microsoft.Network/networkSecurityGroups"
          }
        ],
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/networkSecurityGroups/myVM2NSG/securityRules/default-allow-ssh",
        "resourceGroup": "Task2",
        "resourceName": "myVM2NSG/default-allow-ssh",
        "resourceType": "Microsoft.Network/networkSecurityGroups/securityRules"
      },
      {
        "dependsOn": [
          {
            "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/virtualNetworks/myVM01VNET",
            "resourceGroup": "Task2",
            "resourceName": "myVM01VNET",
            "resourceType": "Microsoft.Network/virtualNetworks"
          }
        ],
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/virtualNetworks/myVM01VNET/subnets/myVM01Subnet",
        "resourceGroup": "Task2",
        "resourceName": "myVM01VNET/myVM01Subnet",
        "resourceType": "Microsoft.Network/virtualNetworks/subnets"
      },
      {
        "dependsOn": [
          {
            "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/virtualNetworks/myVM2VNET",
            "resourceGroup": "Task2",
            "resourceName": "myVM2VNET",
            "resourceType": "Microsoft.Network/virtualNetworks"
          }
        ],
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/virtualNetworks/myVM2VNET/subnets/myVM2Subnet",
        "resourceGroup": "Task2",
        "resourceName": "myVM2VNET/myVM2Subnet",
        "resourceType": "Microsoft.Network/virtualNetworks/subnets"
      },
      {
        "dependsOn": [
          {
            "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/publicIPAddresses/myVM01PublicIP",
            "resourceGroup": "Task2",
            "resourceName": "myVM01PublicIP",
            "resourceType": "Microsoft.Network/publicIPAddresses"
          },
          {
            "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/virtualNetworks/myVM01VNET/subnets/myVM01Subnet",
            "resourceGroup": "Task2",
            "resourceName": "myVM01VNET/myVM01Subnet",
            "resourceType": "Microsoft.Network/virtualNetworks/subnets"
          },
          {
            "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/networkSecurityGroups/myVM01NSG",
            "resourceGroup": "Task2",
            "resourceName": "myVM01NSG",
            "resourceType": "Microsoft.Network/networkSecurityGroups"
          }
        ],
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/networkInterfaces/myVM01VMNic",
        "resourceGroup": "Task2",
        "resourceName": "myVM01VMNic",
        "resourceType": "Microsoft.Network/networkInterfaces"
      },
      {
        "dependsOn": [
          {
            "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/publicIPAddresses/myVM2VNET",
            "resourceGroup": "Task2",
            "resourceName": "myVM2VNET",
            "resourceType": "Microsoft.Network/publicIPAddresses"
          },
          {
            "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/virtualNetworks/myVM2VNET/subnets/myVM2Subnet",
            "resourceGroup": "Task2",
            "resourceName": "myVM2VNET/myVM2Subnet",
            "resourceType": "Microsoft.Network/virtualNetworks/subnets"
          },
          {
            "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/networkSecurityGroups/myVM2NSG",
            "resourceGroup": "Task2",
            "resourceName": "myVM2NSG",
            "resourceType": "Microsoft.Network/networkSecurityGroups"
          }
        ],
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/networkInterfaces/myVM2VMNic",
        "resourceGroup": "Task2",
        "resourceName": "myVM2VMNic",
        "resourceType": "Microsoft.Network/networkInterfaces"
      }
    ],
    "duration": "PT29.5832712S",
    "error": null,
    "mode": "Incremental",
    "onErrorDeployment": null,
    "outputResources": [
      {
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Compute/virtualMachines/myVM2",
        "resourceGroup": "Task2"
      },
      {
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/networkInterfaces/myVM01VMNic",
        "resourceGroup": "Task2"
      },
      {
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/networkInterfaces/myVM2VMNic",
        "resourceGroup": "Task2"
      },
      {
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/networkSecurityGroups/myVM01NSG",
        "resourceGroup": "Task2"
      },
      {
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/networkSecurityGroups/myVM01NSG/securityRules/default-allow-ssh",
        "resourceGroup": "Task2"
      },
      {
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/networkSecurityGroups/myVM2NSG",
        "resourceGroup": "Task2"
      },
      {
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/networkSecurityGroups/myVM2NSG/securityRules/default-allow-ssh",
        "resourceGroup": "Task2"
      },
      {
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/publicIPAddresses/myVM01PublicIP",
        "resourceGroup": "Task2"
      },
      {
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/publicIPAddresses/myVM2VNET",
        "resourceGroup": "Task2"
      },
      {
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/virtualNetworks/myVM01VNET",
        "resourceGroup": "Task2"
      },
      {
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/virtualNetworks/myVM01VNET/subnets/myVM01Subnet",
        "resourceGroup": "Task2"
      },
      {
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/virtualNetworks/myVM2VNET",
        "resourceGroup": "Task2"
      },
      {
        "id": "/subscriptions/b6f09cb5-d2c7-4224-8ff5-8212890faa92/resourceGroups/Task2/providers/Microsoft.Network/virtualNetworks/myVM2VNET/subnets/myVM2Subnet",
        "resourceGroup": "Task2"
      }
    ],
    "outputs": null,
    "parameters": {
      "networkInterfaces_myVM01VMNic_name": {
        "type": "String",
        "value": "myVM01VMNic"
      },
      "networkInterfaces_myVM2VMNic_name": {
        "type": "String",
        "value": "myVM2VMNic"
      },
      "networkSecurityGroups_myVM01NSG_name": {
        "type": "String",
        "value": "myVM01NSG"
      },
      "networkSecurityGroups_myVM2NSG_name": {
        "type": "String",
        "value": "myVM2NSG"
      },
      "publicIPAddresses_myVM01PublicIP_name": {
        "type": "String",
        "value": "myVM01PublicIP"
      },
      "publicIPAddresses_myVM2PublicIP_name": {
        "type": "String",
        "value": "myVM2VNET"
      },
      "virtualMachines_myVM2_name": {
        "type": "String",
        "value": "myVM2"
      },
      "virtualNetworks_myVM01VNET_name": {
        "type": "String",
        "value": "myVM01VNET"
      },
      "virtualNetworks_myVM2VNET_name": {
        "type": "String",
        "value": "myVM2VNET"
      }
    },
    "parametersLink": null,
    "providers": [
      {
        "id": null,
        "namespace": "Microsoft.Network",
        "providerAuthorizationConsentState": null,
        "registrationPolicy": null,
        "registrationState": null,
        "resourceTypes": [
          {
            "aliases": null,
            "apiProfiles": null,
            "apiVersions": null,
            "capabilities": null,
            "defaultApiVersion": null,
            "locationMappings": null,
            "locations": [
              "westus"
            ],
            "properties": null,
            "resourceType": "networkSecurityGroups",
            "zoneMappings": null
          },
          {
            "aliases": null,
            "apiProfiles": null,
            "apiVersions": null,
            "capabilities": null,
            "defaultApiVersion": null,
            "locationMappings": null,
            "locations": [
              "westus"
            ],
            "properties": null,
            "resourceType": "publicIPAddresses",
            "zoneMappings": null
          },
          {
            "aliases": null,
            "apiProfiles": null,
            "apiVersions": null,
            "capabilities": null,
            "defaultApiVersion": null,
            "locationMappings": null,
            "locations": [
              "westus"
            ],
            "properties": null,
            "resourceType": "virtualNetworks",
            "zoneMappings": null
          },
          {
            "aliases": null,
            "apiProfiles": null,
            "apiVersions": null,
            "capabilities": null,
            "defaultApiVersion": null,
            "locationMappings": null,
            "locations": [
              null
            ],
            "properties": null,
            "resourceType": "networkSecurityGroups/securityRules",
            "zoneMappings": null
          },
          {
            "aliases": null,
            "apiProfiles": null,
            "apiVersions": null,
            "capabilities": null,
            "defaultApiVersion": null,
            "locationMappings": null,
            "locations": [
              null
            ],
            "properties": null,
            "resourceType": "virtualNetworks/subnets",
            "zoneMappings": null
          },
          {
            "aliases": null,
            "apiProfiles": null,
            "apiVersions": null,
            "capabilities": null,
            "defaultApiVersion": null,
            "locationMappings": null,
            "locations": [
              "westus"
            ],
            "properties": null,
            "resourceType": "networkInterfaces",
            "zoneMappings": null
          }
        ]
      },
      {
        "id": null,
        "namespace": "Microsoft.Compute",
        "providerAuthorizationConsentState": null,
        "registrationPolicy": null,
        "registrationState": null,
        "resourceTypes": [
          {
            "aliases": null,
            "apiProfiles": null,
            "apiVersions": null,
            "capabilities": null,
            "defaultApiVersion": null,
            "locationMappings": null,
            "locations": [
              "westus"
            ],
            "properties": null,
            "resourceType": "virtualMachines",
            "zoneMappings": null
          }
        ]
      }
    ],
    "provisioningState": "Succeeded",
    "templateHash": "10466536781114221471",
    "templateLink": null,
    "timestamp": "2024-01-13T13:25:21.603672+00:00",
    "validatedResources": null
  },
  "resourceGroup": "Task2",
  "tags": null,
  "type": "Microsoft.Resources/deployments"
