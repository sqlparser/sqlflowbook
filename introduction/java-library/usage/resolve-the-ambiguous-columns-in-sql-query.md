# Resolve the ambiguous columns in SQL query

Given the following SQL:

```sql
select ename
from emp, dept
where emp.deptid = dept.id
```

Column `ename` in the first line is not qualified by table name `emp`, so it’s ambiguous to know which table this column belongs to?

#### solution 1, provides create table DDL

Put the following DDL before the above SQL statement in the same SQL file. the column `ename` will be linked to the table `emp` correctly.

```sql
create table emp(
	id int,
	ename char(50),
	deptid int
);

create table dept(
	id int,
	dname char(50)
);
```

#### solution 2: provide metadata exported from database

Since dlineage v2.2.0 (2022/7/21), This dlineage tool supports `/env` parameter to accept a metadata json file which includes the metadata exported from a database.

By providing metadata.json that includes the metadata, column `ename` should be linked to the table `emp` correctly.

You can use `/env` to specify a metadata.json like this:

```
java -jar gudusoft.dlineage.jar /t oracle /f path_to_sql_file /env metadata.json
```

You can always extract metadata from the database use the [sqlflow-ingester](https://github.com/sqlparser/sqlflow\_public/releases) tool.
