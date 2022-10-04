# /sqlflow/job/displayUserJobsSummary

#### Get all jobs (include history jobs) status and summary

{% swagger src="../../../.gitbook/assets/swagger.yaml" path="/sqlflow/job/displayUserJobsSummary" method="post" %}
[swagger.yaml](../../../.gitbook/assets/swagger.yaml)
{% endswagger %}

Sample response

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
