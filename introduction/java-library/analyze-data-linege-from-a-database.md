# Analyze data linege from a database

Since version 2.2.0, the dlineage tool no longer connect to the database to analyze the data lineage directly. Instead, it accepts a metadata json file which includes all metadata of a database and analyze the data lineage from this json file.

### Extract metdata from database

[sqlflow-ingester](https://github.com/sqlparser/sqlflow\_public/releases) is a tool that extract metadata from various database, you can download the tool here: https://github.com/sqlparser/sqlflow\_public/releases\\

You can find more details for [sqlflow-ingester](https://github.com/sqlparser/sqlflow\_public/releases) here:

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}

Under linux:

```
./exporter.sh -host 127.0.0.1 -port 1521 -db orcl -user scott -pwd tiger -save /tmp/sqlflow-ingester -dbVendor dbvoracle
```

Under windows:

```
exporter.bat -host 127.0.0.1 -port 1521 -db orcl -user scott -pwd tiger -save c:\tmp\sqlflow-ingester -dbVendor dbvoracle
```

After successfully export metadta from the database, you will get a metadata.json file.

### Analyze metadata file

After you get the metadata.json file, just analyze it like a normal sql file with `/f` parmeter:

```
java -jar gudusoft.dlineage.jar /t oracle /f metadata.json
```
