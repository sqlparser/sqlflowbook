# /sqlflow/generation/sqlflow

#### Generate sqlflow model

{% swagger src="../../../.gitbook/assets/swagger.yaml" path="/sqlflow/generation/sqlflow" method="post" %}
[swagger.yaml](../../../.gitbook/assets/swagger.yaml)
{% endswagger %}

Sample resposne:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<dlineage>
    <process id="8" name="Query Insert-1" procedureName="batchQueries" queryHashId="04ebc5aec1a07e1db80b0bc798742875" 
        type="sstinsert" coordinate="[1,1,0],[1,73,0]"/>
    <table id="4" name="raw_customers" type="table" processIds="8" coordinate="[1,13,0],[1,26,0]">
        <column id="5" name="id" coordinate="[1,28,0],[1,30,0]"/>
        <column id="6" name="first_name" coordinate="[1,32,0],[1,42,0]"/>
        <column id="7" name="last_name" coordinate="[1,44,0],[1,53,0]"/>
    </table>
</dlineage>
```
