---
description: >-
  https://github.com/sqlparser/sqlflow_public/blob/master/api/sqlflow-job-api-tutorial.md
---

# Export the data lineage result

When the job status is **success**, you can export the data lineage in json, csv, graphml formats

### Export data lineage in json format

```
/gspLive_backend/sqlflow/job/exportLineageAsJson
```

Example in `Curl`

```
curl -X POST "https://api.gudusoft.com/gspLive_backend/sqlflow/job/exportLineageAsJson" -F "userId=YOUR USER ID HERE" -F "token=YOUR TOKEN HERE" -F "jobId=c359aef4bd9641d697732422debd8055" --output lineage.json
```

**Note:**

> If you want to get table to table relation, please add option -F "tableToTable=true"

### Export data lineage in csv format

```
/gspLive_backend/sqlflow/job/exportFullLineageAsCsv
```

Example in `Curl`

```
curl -X POST "https://api.gudusoft.com/gspLive_backend/sqlflow/job/exportFullLineageAsCsv" -F "userId=YOUR USER ID HERE" -F "token=YOUR TOKEN HERE" -F "jobId=c359aef4bd9641d697732422debd8055" --output lineage.csv
```

**Note:**

> If you want to get table to table relation, please add option -F "tableToTable=true"

> If you want to change csv delimiter, please add option -F "delimiter=\<delimiter char>"

### Export data lineage in graphml format

```
/gspLive_backend/sqlflow/job/exportLineageAsGraphml
```

you can view the lineage graph at yEd Graph Editor.

Example in `Curl`

```
curl -X POST "https://api.gudusoft.com/gspLive_backend/sqlflow/job/exportLineageAsGraphml" -F "userId=YOUR USER ID HERE" -F "token=YOUR TOKEN HERE" -F "jobId=c359aef4bd9641d697732422debd8055" --output lineage.graphml
```

**Note:**

> If you want to get table to table relation, please add option -F "tableToTable=true"
