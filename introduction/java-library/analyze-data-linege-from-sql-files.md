# Analyze data linege from SQL files

Use `/f` parameter to specify a single SQL file, or use `/d` parameter to specfify a directory that inculdes multiple SQL files.

```shell
java -jar gudusoft.dlineage.jar /t mssql /f path_to_sql_file
```

An sample sql file could be:

```sql
INSERT INTO raw_customers (id, first_name, last_name) VALUES(0, '', '');
```

An output XML will be generated:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<dlineage>
    <process id="8" name="Query Insert-1" procedureName="batchQueries" queryHashId="04ebc5aec1a07e1db80b0bc798742875" type="sstinsert" coordinate="[1,1,0],[1,73,0]"/>
    <table id="4" name="raw_customers" type="table" processIds="8" coordinate="[1,13,0],[1,26,0]">
        <column id="5" name="id" coordinate="[1,28,0],[1,30,0]"/>
        <column id="6" name="first_name" coordinate="[1,32,0],[1,42,0]"/>
        <column id="7" name="last_name" coordinate="[1,44,0],[1,53,0]"/>
    </table>
</dlineage>
```

Some indications for the above resposne:

* coordinate\<x,y,z>: x is the correspond line number, y is the column number and z is the has code value of the file.
* process: the type of the data lineage
* name: table field name or sql name
