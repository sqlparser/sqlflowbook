# /sqlflow/generation/sqlflow

#### Generate sqlflow model

{% swagger src="../../../.gitbook/assets/swagger.yaml" path="/sqlflow/generation/sqlflow" method="post" %}
[swagger.yaml](../../../.gitbook/assets/swagger.yaml)
{% endswagger %}

Sample resposne:

```json
{
  "code": 200,
  "data": {
    "dbvendor": "dbvoracle",
    "dbobjs": [
      {
        "id": "8",
        "name": "QUERY INSERT-1",
        "type": "process",
        "coordinates": [
          {
            "x": 1,
            "y": 1,
            "hashCode": "0"
          },
          {
            "x": 1,
            "y": 73,
            "hashCode": "0"
          }
        ],
        "queryHashId": "04ebc5aec1a07e1db80b0bc798742875"
      },
      {
        "id": "4",
        "name": "RAW_CUSTOMERS",
        "type": "table",
        "columns": [
          {
            "id": "5",
            "name": "ID",
            "coordinates": [
              {
                "x": 1,
                "y": 28,
                "hashCode": "0"
              },
              {
                "x": 1,
                "y": 30,
                "hashCode": "0"
              }
            ]
          },
          {
            "id": "6",
            "name": "FIRST_NAME",
            "coordinates": [
              {
                "x": 1,
                "y": 32,
                "hashCode": "0"
              },
              {
                "x": 1,
                "y": 42,
                "hashCode": "0"
              }
            ]
          },
          {
            "id": "7",
            "name": "LAST_NAME",
            "coordinates": [
              {
                "x": 1,
                "y": 44,
                "hashCode": "0"
              },
              {
                "x": 1,
                "y": 53,
                "hashCode": "0"
              }
            ]
          }
        ],
        "coordinates": [
          {
            "x": 1,
            "y": 13,
            "hashCode": "0"
          },
          {
            "x": 1,
            "y": 26,
            "hashCode": "0"
          }
        ]
      }
    ],
    "relationships": []
  },
  "sessionId": "527f2887da8bd7f5952840aa14cb05f357943aff3f5f02a6f1d7f914bca12971_1664807322126"
}
```

****[**Try it out!**](../../swagger-ui.md)****
