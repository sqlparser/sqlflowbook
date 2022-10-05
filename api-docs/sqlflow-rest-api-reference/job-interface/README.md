---
description: >-
  https://github.com/sqlparser/sqlflow_public/blob/master/api/sqlflow_api.md#sqlflow-user-job-interface
---

# Job Interface



<figure><img src="../../../.gitbook/assets/job-types (1).png" alt=""><figcaption></figcaption></figure>

### Simple job rest API

**1.** [**Submit a sqlflow job**](./#sqlflow-job-submituserjob)****

Call this API by sending the SQL files and get the result includes the data lineage. SQLFlow job supports both of multiple files and zip archive file.

```
/gspLive_backend/sqlflow/job/submitUserJob
```

Example in `Curl`

```
curl -X POST "https://api.gudusoft.com/gspLive_backend/sqlflow/job/submitUserJob" -H "accept:application/json;charset=utf-8" -H "Content-Type:multipart/form-data" -F "userId=YOUR USER ID HERE" -F "token=YOUR TOKEN HERE" -F "sqlfiles=@FIRST FILE PATH" -F "sqlfiles=@SECOND FILE PATH" -F "dbvendor=dbvmssql" -F "jobName=job1"
```

{% swagger src="../../../.gitbook/assets/swagger.yaml" path="/sqlflow/job/submitUserJob" method="post" %}
[swagger.yaml](../../../.gitbook/assets/swagger.yaml)
{% endswagger %}

**Note:**

* **-H "Content-Type:multipart/form-data"** is required
* Add **@** before the file path

Sample response:

```json
{
	"code":200,
	"data":{
		"jobId":"c359aef4bd9641d697732422debd8055",
		"jobName":"job1",
		"userId":"google-oauth2|104002923119102769706",
		"dbVendor":"dbvmssql",
		"dataSource":{
			
		},
		"fileNames":["1.sql","1.zip"],
		"createTime":"2020-12-15 15:14:39",
		"status":"create"
	}
}
```

Please records the jobId field.



**2. Get job status**

* [Get the specific user job status and summary](sqlflow-job-displayuserjobsummary.md)

```
/gspLive_backend/sqlflow/job/displayUserJobSummary
```

Example in `Curl`

```json
curl -X POST "https://api.gudusoft.com/gspLive_backend/sqlflow/job/displayUserJobSummary" -F "jobId=c359aef4bd9641d697732422debd8055" -F "userId=YOUR USER ID HERE" -F "token=YOUR TOKEN HERE"
```

{% swagger src="../../../.gitbook/assets/swagger.yaml" path="/sqlflow/job/displayUserJobSummary" method="post" %}
[swagger.yaml](../../../.gitbook/assets/swagger.yaml)
{% endswagger %}

Sample response:

```json
{
  "code":200,
  "data":{
  	"jobId":"c359aef4bd9641d697732422debd8055",
  	"jobName":"job1",
  	"userId":"google-oauth2|104002923119102769706",
  	"dbVendor":"dbvmssql",
  	"dataSource":{
  		
  	},
  	"fileNames":["1.sql","1.zip"],
  	"createTime":"2020-12-15 15:14:39",
  	"status":"success",
  	"sessionId":"fe5898d4e1b1a7782352b50a8203ca24c04f5513446e9fb059fc4d584fab4dbf_1608045280033"
  }
}
```

* [Get all jobs (include history jobs) status and summary](sqlflow-job-displayuserjobssummary.md)

```
/gspLive_backend/sqlflow/job/displayUserJobsSummary
```

Example in `Curl`

```json
curl -X POST "https://api.gudusoft.com/gspLive_backend/sqlflow/job/displayUserJobsSummary" -F "userId=YOUR USER ID HERE" -F "token=YOUR TOKEN HERE"
```

{% swagger src="../../../.gitbook/assets/swagger.yaml" path="/sqlflow/job/displayUserJobsSummary" method="post" %}
[swagger.yaml](../../../.gitbook/assets/swagger.yaml)
{% endswagger %}

Sample Response:

```json
{
  "code": 200,
  "data": {
    "total": 2,
    "success": 2,
    "partialSuccess": 0,
    "fail": 0,
    "jobIds": [
      "939fdbbaf52b45139b86c0761d6036b0",
      "44bf162fc5e04ab68289e6e784875203"
    ],
    "jobDetails": [
      {
        "jobId": "939fdbbaf52b45139b86c0761d6036b0",
        "jobName": "yuanhao1",
        "userId": "auth0|632xxxx",
        "userEmail": "xxx@xxx.com",
        "dbVendor": "dbvoracle",
        "showRelationType": "fdd",
        "ignoreRecordSet": true,
        "dataflowOfAggregateFunction": "direct",
        "showConstantTable": false,
        "showTransform": false,
        "ignoreFunction": true,
        "fileNames": [
          "test.sql"
        ],
        "createTime": "2022-10-04 10:45:04",
        "status": "success",
        "sessionId": "24a4455c71fa35c0393d5747f9c23a9d99f32fa4c130a6b8da8d6a7db8d157ae_1664880305725",
        "executeTime": "0min 1sec",
        "executeTimeMillis": 0,
        "onTop": false,
        "parallel": false,
        "persist": false,
        "incremental": false,
        "schedulable": false,
        "cancelSchedule": false,
        "lastExecuteTime": "2022-10-04 10:45:05",
        "subJobs": [],
        "version": "5.2.0"
      },
      {
        "jobId": "44bf162fc5e04ab68289e6e784875203",
        "jobName": "sqlserver sample lineage",
        "userId": "auth0|6326xxxx",
        "userEmail": "xxxx@xxxx.com",
        "dbVendor": "dbvmssql",
        "showRelationType": "fdd",
        "ignoreRecordSet": true,
        "showConstantTable": false,
        "showTransform": false,
        "ignoreFunction": true,
        "fileNames": [
          "metadata.zip"
        ],
        "createTime": "2022-09-18 06:46:20",
        "status": "success",
        "sessionId": "e1bc494a6f683c9e724c5f018d2a0c96d80304a3ddb025caf87dc1ac19e1a785_1636819107871",
        "hasMetadata": true,
        "executeTime": "0min 10sec",
        "executeTimeMillis": 0,
        "onTop": false,
        "parallel": false,
        "persist": false,
        "incremental": false,
        "schedulable": false,
        "cancelSchedule": true
      }
    ]
  }
}
```



**3. Export data lineage**

When the job status is **success**, you can export the data lineage in json, csv, graphml formats

* 3.1 [Export data lineage in json format](sqlflow-job-exportlineageasjson.md)

```
/gspLive_backend/sqlflow/job/exportLineageAsJson
```

Example in `Curl`

```
curl -X POST "https://api.gudusoft.com/gspLive_backend/sqlflow/job/exportLineageAsJson" -F "userId=YOUR USER ID HERE" -F "token=YOUR TOKEN HERE" -F "jobId=c359aef4bd9641d697732422debd8055" --output lineage.json
```

{% swagger src="../../../.gitbook/assets/swagger.yaml" path="/sqlflow/job/exportLineageAsJson" method="post" %}
[swagger.yaml](../../../.gitbook/assets/swagger.yaml)
{% endswagger %}

**Note:**

> If you want to get table to table relation, please add option -F "tableToTable=true"

Sample Response is a file in Json format:

```json
{
	"jobId":"939fdbbaf52b45139b86c0761d6036b0",
	"code":200,
	"data":{
		"mode":"global",
		"summary":{
			"schema":0,
			"process":1,
			"database":0,
			"view":0,
			"mostRelationTables":[],
			"column":3,
			"relationship":0,
			"table":1
		},
		"sqlflow":{
			"dbvendor":"dbvoracle",
			"relationships":[],
			"dbobjs":[
				{
					"queryHashId":"04ebc5aec1a07e1db80b0bc798742875",
					"name":"QUERY INSERT-1",
					"coordinates":[
						{
							"hashCode":"0",
							"x":1,
							"y":1
						},
						{
							"hashCode":"0",
							"x":1,
							"y":73
						}
					],
					"id":"8",
					"type":"process"
				},
				{
					"columns":[
						{
							"name":"ID",
							"coordinates":[
								{
									"hashCode":"0",
									"x":1,
									"y":28
								},
								{
									"hashCode":"0",
									"x":1,
									"y":30
								}
							],
							"id":"5"
						},
						{
							"name":"FIRST_NAME",
							"coordinates":[
								{
									"hashCode":"0",
									"x":1,
									"y":32
								},
								{
									"hashCode":"0",
									"x":1,
									"y":42
								}
							],
							"id":"6"
						},
						{
							"name":"LAST_NAME",
							"coordinates":[
								{
									"hashCode":"0",
									"x":1,
									"y":44
								},
								{
									"hashCode":"0",
									"x":1,
									"y":53
								}
							],
							"id":"7"
						}
					],
					"name":"RAW_CUSTOMERS",
					"coordinates":[
						{
							"hashCode":"0",
							"x":1,
							"y":13
						},
						{
							"hashCode":"0",
							"x":1,
							"y":26
						}
					],
					"id":"4",
					"type":"table"
				}
			]
		},
		"graph":{
			"relationshipIdMap":{},
			"elements":{
				"tables":[],
				"edges":[]
			},
			"tooltip":{},
			"listIdMap":{}
		}
	},
	"sessionId":"24a4455c71fa35c0393d5747f9c23a9d99f32fa4c130a6b8da8d6a7db8d157ae_1664880305725"
}
```

* 3.2 [Export data lineage in csv format](sqlflow-job-exportfulllineageascsv.md)

```
/gspLive_backend/sqlflow/job/exportFullLineageAsCsv
```

Example in `Curl`

```
curl -X POST "https://api.gudusoft.com/gspLive_backend/sqlflow/job/exportFullLineageAsCsv" -F "userId=YOUR USER ID HERE" -F "token=YOUR TOKEN HERE" -F "jobId=c359aef4bd9641d697732422debd8055" --output lineage.csv
```

{% swagger src="../../../.gitbook/assets/swagger.yaml" path="/sqlflow/job/exportFullLineageAsCsv" method="post" %}
[swagger.yaml](../../../.gitbook/assets/swagger.yaml)
{% endswagger %}

**Note:**

> If you want to get table to table relation, please add option -F "tableToTable=true"

> If you want to change csv delimiter, please add option -F "delimiter=\<delimiter char>"

* 3.3 [Export data lineage in graphml format with which you can view the lineage graph at yEd Graph Editor](sqlflow-job-exportlineageasgraphml.md)

```
/gspLive_backend/sqlflow/job/exportLineageAsGraphml
```

Example in `Curl`

```
curl -X POST "https://api.gudusoft.com/gspLive_backend/sqlflow/job/exportLineageAsGraphml" -F "userId=YOUR USER ID HERE" -F "token=YOUR TOKEN HERE" -F "jobId=c359aef4bd9641d697732422debd8055" --output lineage.graphml
```

{% swagger src="../../../.gitbook/assets/swagger.yaml" path="/sqlflow/job/exportLineageAsGraphml" method="post" %}
[swagger.yaml](../../../.gitbook/assets/swagger.yaml)
{% endswagger %}

**Note:**

> If you want to get table to table relation, please add option -F "tableToTable=true"

**----------------------------------------------TODO---------------------------------------------**

#### 4. Regular job rest API

**1. Submit a regular job**

Call this API by sending the SQL files and get the result includes the data lineage. SQLFlow job supports both of multiple files and zip archive file.

Set incremental=true If the job is incremental.&#x20;

* jobId should be null for the first submit and please note down the jobId field from response message
* jobId cannot be null for next submit. Give the jobId which is returned in the first submit response.

```
/gspLive_backend/sqlflow/job/submitPersistJob
```

{% swagger src="../../../.gitbook/assets/swagger.yaml" path="/sqlflow/job/submitPersistJob" method="post" %}
[swagger.yaml](../../../.gitbook/assets/swagger.yaml)
{% endswagger %}

Example in `Curl`

```
curl -X POST "https://api.gudusoft.com/gspLive_backend/sqlflow/job/submitPersistJob" -H "accept:application/json;charset=utf-8" -H "Content-Type:multipart/form-data" -F "userId=YOUR USER ID HERE" -F "token=YOUR TOKEN HERE" -F "sqlfiles=@FIRST FILE PATH" -F "sqlfiles=@SECOND FILE PATH" -F "dbvendor=dbvmssql" -F "jobName=job1" -F "incremental=true"
```

Incremental submit in `Curl`

```
curl -X POST "https://api.gudusoft.com/gspLive_backend/sqlflow/job/submitPersistJob" -H "accept:application/json;charset=utf-8" -H "Content-Type:multipart/form-data" -F "userId=YOUR USER ID HERE" -F "token=YOUR TOKEN HERE" -F "sqlfiles=@FIRST FILE PATH" -F "sqlfiles=@SECOND FILE PATH" -F "dbvendor=dbvmssql" -F "jobName=job1" -F "incremental=true" -F "jobId=JobId OF FIRST SUBMIT"
```

**Note:**

* **-H "Content-Type:multipart/form-data"** is required
* Add **@** before the file path

Return data:

```json
{
	"code":200,
	"data":{
		"jobId":"c359aef4bd9641d697732422debd8055",
		"jobName":"job1",
		"userId":"google-oauth2|104002923119102769706",
		"dbVendor":"dbvmssql",
		"dataSource":{
			
		},
		"fileNames":["1.sql","1.zip"],
		"createTime":"2020-12-15 15:14:39",
		"status":"create"
	}
}
```

Please records the jobId field.
