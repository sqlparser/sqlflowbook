---
description: >-
  https://github.com/sqlparser/sqlflow_public/blob/master/api/sqlflow_api.md#sqlflow-generation-interface
---

# Generation Interface

* Generate sqlflow model
  * [/sqlflow/generation/sqlflow](sqlflow-generation-sqlflow.md#generate-sqlflow-model)
* Export lineage as CSV
  * [/sqlflow/generation/sqlflow/exportLineageAsCsv](sqlflow-generation-sqlflow-exportlineageascsv.md#export-lineage-as-csv)

#### ****[**Generate the data lineage**](sqlflow-generation-sqlflow.md)

Send the SQL query and get the data lineage result.

```
/gspLive_backend/sqlflow/generation/sqlflow
```

{% swagger src="../../../.gitbook/assets/swagger.yaml" path="/sqlflow/generation/sqlflow" method="post" %}
[swagger.yaml](../../../.gitbook/assets/swagger.yaml)
{% endswagger %}

* **SQLFlow Cloud Server**

```
curl -X POST "https://api.gudusoft.com/gspLive_backend/sqlflow/generation/sqlflow?showRelationType=fdd" -H  "Request-Origion:testClientDemo" -H  "accept:application/json;charset=utf-8" -H  "Content-Type:multipart/form-data" -F "sqlfile=" -F "dbvendor=dbvoracle" -F "ignoreRecordSet=false" -F "simpleOutput=false" -F "sqltext=CREATE VIEW vsal  as select * from emp" -F "userId=YOUR USER ID HERE"  -F "token=YOUR TOKEN HERE"
```

* **SQLFlow on-premise version**

```
curl -X POST "http://127.0.0.1:8081/gspLive_backend/sqlflow/generation/sqlflow?showRelationType=fdd"    -H  "Request-Origion:testClientDemo" -H  "accept:application/json;charset=utf-8" -H  "Content-Type:multipart/form-data" -F "sqlfile=" -F "dbvendor=dbvoracle" -F "ignoreRecordSet=false" -F "simpleOutput=false" -F "sqltext=CREATE VIEW vsal  as select * from emp" -F "userId=gudu|0123456789" 
```

#### ****[**Export the data lineage in csv format**](sqlflow-generation-sqlflow-exportlineageascsv.md)****

Send the SQL file and get the csv result which includes the data lineage.

```
/gspLive_backend/sqlflow/generation/sqlflow/exportLineageAsCsv
```

{% swagger src="../../../.gitbook/assets/swagger.yaml" path="/sqlflow/generation/sqlflow/exportLineageAsCsv" method="post" %}
[swagger.yaml](../../../.gitbook/assets/swagger.yaml)
{% endswagger %}

```
curl -X POST "https://api.gudusoft.com/gspLive_backend/sqlflow/generation/sqlflow/exportLineageAsCsv" -H  "accept:application/json;charset=utf-8" -H  "Content-Type:multipart/form-data" -F "userId=YOUR USER ID HERE" -F "token=YOUR TOKEN HERE" -F "dbvendor=dbvoracle" -F "showRelationType=fdd" -F "sqlfile=@YOUR UPLOAD FILE PATH HERE" --output YOUR DOWNLOAD FILE PATH HERE
```

Sample:

```
curl -X POST "https://api.gudusoft.com/gspLive_backend/sqlflow/generation/sqlflow/exportLineageAsCsv" -H  "accept:application/json;charset=utf-8" -H  "Content-Type:multipart/form-data" -F "userId=auth0|5fc8e95991a780006f180d4d" -F "token=YOUR TOKEN HERE" -F "dbvendor=dbvoracle" -F "showRelationType=fdd" -F "sqlfile=@c:\prg\tmp\demo.sql" --output c:\prg\tmp\demo.csv
```

**Note:**

* \-H "Content-Type:multipart/form-data" is required.
* Add **@** before the upload file path
* \--output is required.
* Optional, if you just want to fetch table to table relations, please add **-F "tableToTable=true"**
