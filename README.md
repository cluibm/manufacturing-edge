# manufacturing-edge

Our team implemented a quality inspection system using edge computing technologies like IBM Edge Application Manager. We have described our implementation in the article, [Explore the details of an edge computing architecture for a quality inspection system](), where you can learn how IBM Edge Application Manager and IBM Maximo Visual Inspection work together to deliver an edge computing solution.

We implemented several functions to be able to access the corresponding entities from IBM Edge Application Manager (IEAM) APIs.

## The following functions were implemented for accessing the corresponding entities from [IBM Edge Application Manager (IEAM) APIs](https://www.ibm.com/support/knowledgecenter/SSFKVV_4.2/api/edge_rest_apis.html):
Table 1 documents IEAM Exchange API and Table 2 documents IEAM CSS API.

### Table 1. IEAM Exchange API (base is HZN_EXCHANGE_API)
Component |	Name |	API	| Description
---- | ---- | ---- | ----
Nodes |	getNodeStatus |	GET /orgs/{org_id}/nodes/{node_id}/status |	Retrieves node health check information, such as running services, connectivity, and last response time
|	| getNodes|	GET /orgs/{org_id}/nodes	|Retrieves a list of nodes registered at IEAM Exchange
|	| getNode |	GET /orgs/{org_id}/nodes/{node_id}	Retrieves information about a specified node registered in IEAM Exchange
|Services	| getServices | 	GET /orgs/{org_id} /services	| Retrieves list of services defined at IEAM Exchange
| | getService |	GET /orgs/{org_id}/services/{service_id}	| Retrieves information about a specified service defined in IEAM Exchange
| |publishService	|POST /orgs/{org_id}/services/{service_id}	|Updates the service definition in IEAM Exchange or creates it if it does not exist
|Patterns|	getPatterns|	GET /orgs/{org_id/patterns	|Retrieves a list of patterns defined in IEAM Exchange
| |getPattern|	GET /orgs/{org_id}/patterns/{pattern_id}	|Retrieves information about specified pattern defined in IEAM Exchange
| |publishPattern|	POST /orgs/{org_id}/patterns/{pattern_id}|	Updates the pattern definition in IEAM Exchange or creates it if not exists
| | setPatternKey |	PUT /orgs/{org_id}/patterns/{pattern_id}/keys/{key_name}	| Updates IEAM node public key for a specified pattern
| Policies|	getNodePolicy | GET /orgs/{org_id}/nodes/{node_id}/policy	|Retrieves node policy properties and constraints
| |updateNodePolicy	|PUT /orgs/{org_id}/nodes/{node_id}/policy|	Updates node policy properties and/or constraints
|Agreements|	getNodeAgreements	|GET /orgs/{org_id}/nodes/{node_id}/agreements|	Retrieves a list of agreements for specified IEAM node
| | getNodeAgreement|GET /orgs/{org_id}/nodes/{node_id}/agreements/{agmt_id}	|Retrieves information about specified IEAM node agreement
			
 

### Table 2. IEAM CSS API (base is HZN_MMS_API)

Name |	API	|Description
----|----|----
getStatus|	GET /health	|Retrieves the IEAM CSS health check information
createObject	|PUT /objects/{org_id}/{object_type}/{object_id}	|Updates IEAM CSS object definition or creates if it does not exist
publishBinaryData|	PUT /objects/{org_id}/{object_type}/{object_id}/data	|Updates binary data for a specified IEAM CSS object (model files for us) or creates it if it does not exist
getObject|	GET /objects/{org_id}/{object_type}/{object_id}	|Retrieves specified IEAM CSS object definition information
getObjects|	GET /objects/{org_id}/{object_type}?all_objects=true	|Retrieves a list of IEAM CSS objects filtered by their type
deleteObject|	DELETE /objects/{org_id}/{object_type}/{object_id}	|Deletes a specified IEAM CSS object from database

