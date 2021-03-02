An Azure storage account contains all of your Azure Storage data objects: blobs, files, queues, tables, and disks. The storage account provides a unique namespace for your Azure Storage data that is accessible from anywhere in the world over HTTP or HTTPS. Data in your Azure storage account is durable and highly available, secure, and massively scalable.

# Version 1.0.0.0

```
{
	"type": "Microsoft.Resources/deployments",
	"apiVersion": "2020-06-01",
	"name": "[concat(deployment().name, '-', variables('storageAccountName'))]",
	"properties": {
		"mode": "Incremental",
		"templateLink": {
			"id": "[resourceId('ComponentSpecs', 'Microsoft.Resources/templateSpecs/versions', 'StorageAccount', '1.0.0.0')]"
		},
		"parameters":{
			"name" :{
				"value": "[variables('storageAccountName')]"
			}
		}
	}
}
```

## Parameters

Name | Mandatory | Default Value
------------ | ------------- | -------------
name | yes | 
location | no | [resourceGroup().location]

## Outputs

Name | Type 
------------ | ------------- 
resourceId | string 