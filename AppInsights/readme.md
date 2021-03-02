Collect, analyze, and act on telemetry data from your Azure and on-premises environments. Azure Monitor helps you maximize performance and availability of your applications and proactively identify problems in seconds.

# Version 1.0.0.0

```
{
	"type": "Microsoft.Resources/deployments",
	"apiVersion": "2020-06-01",
	"name": "[concat(deployment().name, '-', variables('appInsightsName'))]",
	"properties": {
		"mode": "Incremental",
		"templateLink": {
			"id": "[resourceId('ComponentSpecs', 'Microsoft.Resources/templateSpecs/versions', 'AppInsights', '1.0.0.0')]"
		},
		"parameters":{
			"name" :{
				"value": "[variables('appInsightsName')]"
			}
		}
	}
}
```

## Parameters

Name | Mandatory | Type | Default Value
------------ | ------------- | ------------- | -------------
name | yes | string |
location | no | string| [resourceGroup().location]
applicationId | no | string | [EMPTY]
applicationType | no | bool | web

## Outputs

Name | Type 
------------ | ------------- 
resourceId | string 
instrumentationKey | string
