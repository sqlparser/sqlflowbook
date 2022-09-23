---
description: >-
  https://github.com/sqlparser/sqlflow_public/blob/master/doc/get-started/dataflow-column-used-in-aggregate-function.md
---

# Dataflow: column used in aggregate function

Aggregate function usually takes column as an argument, in this article, we will discuss what kind of dataflow will be created between the column used as function argument and the aggregate function.

### 1. COUNT()

COUN() may takes a star column, or any column name or even empty argument.

If the argument is empty or a star column, no dataflow will be generated between the argument and function.

#### 1.1 A direct dataflow

```sql
SELECT count(empId) total_num
FROM scott.emp
```

By default, a direct dataflow will be generted by between the empId column and COUNT() function.

```
scott.emp.empId -> direct -> COUNT()
```

This dataflow may seems strange since the result value of COUNT() doesn't depends on the value of empId column but this can be an option if our users prefer to have such dataflow.

<figure><img src="../../.gitbook/assets/68747470733a2f2f696d616765732e67697465652e636f6d2f75706c6f6164732f696d616765732f323032312f313230362f3232353530345f63343963333735305f383133363830392e706e67.webp" alt=""><figcaption></figcaption></figure>

#### 1.2 No dataflow

You can use an option to not to generating a dataflow between empId and COUNT() if prefered.

Kind remind: no matter whether a direct dataflow is generated between the empId and COUNT() or not, the following indirect dataflow will always be created.

```
scott.emp.RelationRows -> indirect -> COUNT()
```

### 2. Aggregate function exclude COUNT()

COUNT() function is a little bit different when creating dataflow. All other aggregate functions such as SUM() will create a direct dataflow with the column used as the argument.

```sql
SELECT deptno, SUM(SAL) sal_sum
FROM scott.emp
group by deptno
```

A direct dataflow will be created from SAL to SUM().

```sql
scott.emp.SAL -> direct -> SUM()
```

<figure><img src="../../.gitbook/assets/68747470733a2f2f696d616765732e67697465652e636f6d2f75706c6f6164732f696d616765732f323032312f313230362f3136303134325f35343538306633615f383133363830392e706e67.webp" alt=""><figcaption></figcaption></figure>
