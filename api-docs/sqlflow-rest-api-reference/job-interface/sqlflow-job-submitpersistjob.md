# /sqlflow/job/submitPersistJob

#### **Submit a regular job**

{% swagger src="../../../.gitbook/assets/swagger.yaml" path="/sqlflow/job/submitPersistJob" method="post" %}
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
		"status":"create"
	}
}
```

[**Try it out!**](../../swagger-ui.md)****
