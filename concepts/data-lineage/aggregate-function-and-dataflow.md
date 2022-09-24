---
description: >-
  https://github.com/sqlparser/sqlflow_public/blob/master/doc/get-started/dataflow-column-used-in-aggregate-function.md
---

# Aggregate function and Dataflow

Aggregate function usually take column as an argument. in this article, we will discuss what kind of dataflow will be created between the column used and the aggregate function.

### 1. Aggregate function

All Aggregate function except COUNT(such as SUM, AVERAGE etc...) will create a direct dataflow with the column used in its argument.

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

### 2. COUNT()

COUN() may take star, any other column or even empty argument. COUNT() function is a little bit different when creating dataflow.

If the argument is empty or a star column, no dataflow will be generated between the argument and function.

#### 2.1 A direct dataflow

```sql
SELECT count(empId) total_num
FROM scott.emp
```

A direct dataflow will be generted by between the empId column and COUNT() function by default.

```
scott.emp.empId -> direct -> COUNT()
```

This dataflow may seem strange since the result value of COUNT() doesn't depend on the value of empId column but this can be configured in the setting tab if the users prefer to have such dataflow.

<figure><img src="../../.gitbook/assets/68747470733a2f2f696d616765732e67697465652e636f6d2f75706c6f6164732f696d616765732f323032312f313230362f3232353530345f63343963333735305f383133363830392e706e67.webp" alt=""><figcaption></figcaption></figure>

#### 2.2 No dataflow

We can switch off generating a dataflow between empId and COUNT() if prefered.

Kindly remind: no matter whether a direct dataflow is generated between the empId and COUNT() or not, the following indirect dataflow will always be created at our backend. We can choose to explicitly display this dataflow or not.

```
scott.emp.RelationRows -> indirect -> COUNT()
```
