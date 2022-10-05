# /sqlflow/job/displayUserJobSummary

#### Get the specific user job status and summary

{% swagger src="../../../.gitbook/assets/swagger.yaml" path="/sqlflow/job/displayUserJobSummary" method="post" %}
[swagger.yaml](../../../.gitbook/assets/swagger.yaml)
{% endswagger %}

Sample response:

```json
{
  "code": 200,
  "data": {
    "jobId": "939fdbbaf52b45139b86c0761d6036b0",
    "jobName": "yuanhao1",
    "userId": "auth0|6326bxxxx",
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
  }
}
```
