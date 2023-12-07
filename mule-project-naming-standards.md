## Mule4 Project Naming Standards
| Artifact Type | Naming Convention | Format | Example|
| ------- | ----- | ------------- | ------------- |
| Project Name | short code that is unique to the domain,logical name of the application,the API layer |_{domain}-{app}-{layer}_|_hr-employee-benefits-papi_|
| Router-implementation| This is the main flow of the application, It should be kept in the implementation folder|_{application-name}-main.xml_|_hr-employee-benefits-papi-main.xml_ |
| RAML Application Name | The main RAML file should have the same name as the project |{domain}-{app}-{layer}.raml|hr-employee-benefits-eapi.raml|
| Folder Name in RAML | We should always use camelCase |dataTypes|dataTypes|
| Folder Name in src/main/mule  | This folder is used for common configurations like global configurations, secured configurations, common-errors and common config |common|common|
| Non Secured Connector Configuration  | This xml file is used to store the connector configurations which are unsecure |z-global-config.xml|z-global-config.xml|
| Secured Connector Configuration | This xml file is used to store the connector configurations which are secure |z-global-secured-config.xml|z-global-secured-config.xml|
| Common Error | This xml file is used to store the common errors like API Kit errors and common error handling  |z-common-error.xml|z-common-error.xml|
| Common Utility Flows  | This xml file is used to store the reusability code which we want to use across the application |z-common-config.xml|z-common-config.xml|
| implementation  | This xml file contains implementation flows of our application |get,put,post,delete,patch-{domain-context}.xml|post-account-benefits.xml|
| dwl files(lower-kebab-case) | This dwl file is used to store the dataweave transformation code |p-{dataweave-payload-transformation}.dwl (for Payload)|p-publish-generic-event-from-queue-to-db.dwl|
|  | This dwl file is used to store the dataweave variable |v-{dataweave-variable-transformation}.dwl (for Variables)||
| | This dwl file is used to store the common utility |c-{dataweave-common-utility}.dwl (for Common or Utility)|dataTypes|
| examples (TitleCase) | |{EntityName}[Input]|Output].[json,xml,csv]||
| properties(lower-kebab-case)| This file is used to store the connector configuration details example like database and http |"config[-secure][-{env}].[properties or yaml]"|config-prod.yaml|
| Main Flow Name | This is the main flow name of the application |"mf-{Name of the flow}"|mf-get-mail-letter-task|
| Sub Flow Name | This is the subflow name of the application |sf-{Name of the flow}|sf-validate-login|
| Flow Reference Name | This is the flow reference name |Refer to {Name of the flow}|cf-post-generic-event-from-queue-to-db|
| for each component | We need to keep the name of the scope but add an underscore and a brief description of the scope |For Each {Name of the Collection}|For Each shipment-entry|
| variable name | This is the variable name |httpStatus|httpStatus|
| Configuration element names | This is the http listener config in the global.xml file |main_http-listener|main_http-listener|
|| This is the http requester config in the global.xml file |oms_http-requestor|ax_http-requestor|
|| This is the env properties config in the global.xml file |env_properties|env_properties|
|| This is the object store config in the global.xml file |oauth_object-store|oauth_object-store|
|Choice Router| This is the choice router naming convention |" CHECK IF {What is the condition}"|"CHECK IF SalesforceId is not empty"|
|Logger| logger debug naming convention |"LOG [DEBUG/ERROR] {Define the purpose of this log}"|LOG DEBUG Payload Response from Salesforce|
| | logger error naming convention |"LOG [DEBUG/ERROR] {Define the purpose of this log}"|LOG ERROR After Invoking SIMS US SOAP WS|
| Cache Scope | Cache Scope naming convention |"CACHE {Object by CacheKey}"|CACHE Account by accountId|
| Common Flow | This is the common flow which we used across the application |"cf-{Name of the flow lower case}"|cf-logger-init|
| Dataweave Component | This is the dataweave code in the Transform message |DW {Purpose of the transformation}|DW Map Payload with Required Fields|
|Flow Variable | How to set the flow variable name in the Application |FV SET {name of the flow Variable}|FV SET vSalesforceId|
|Set Payload | How to set the Set Payload name in the Application |PL SET {Purpose of the payload}|PL SET Static Payload for Final Response|
|Validator Component | How to set the Validator Component name in the Application |VALIDATE {Object}|VALIDATE Payload|


