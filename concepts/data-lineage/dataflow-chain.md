---
description: >-
  https://github.com/sqlparser/sqlflow_public/blob/master/doc/get-started/dataflow-chain.md
---

# Dataflow chain

If the resultset of a subquery or CTE is used in the from clause of the upper-level statement, then the impact of the lower level resultset will be transferred to the upper-level.

```sql
WITH
  cteReports (EmpID, FirstName, LastName, MgrID, EmpLevel)
  AS
  (
    SELECT EmployeeID, FirstName, LastName, ManagerID, EmpLevel  -- resultset1
    FROM Employees
    WHERE ManagerID IS NULL
  )
SELECT
  count(EmpID), sum(EmpLevel)  -- resultset2
FROM cteReports 
```

In the CTE, there is an impact relation:

```
Employees.ManagerID -> indirect -> RS-1.RelationRows
```

Since `cteReports` is used in the from clause of the upper-level statement, then the impact will carry on like this:

```
Employees.ManagerID -> indirect -> RS-1.RelationRows -> indirect -> CTE-CTEREPORTS.RelataionRows
```

If we ignore the intermediate resultset, the end to end dataflow is :

```
Employees.ManagerID -> indirect -> RS-2.COUNT(EmpID)
Employees.ManagerID -> indirect -> RS-2.SUM(EmpLevel)
```

**diagram**

<figure><img src="../../.gitbook/assets/68747470733a2f2f696d616765732e67697465652e636f6d2f75706c6f6164732f696d616765732f323032312f313230362f3138303931365f36323365363231335f383133363830392e706e67.webp" alt=""><figcaption></figcaption></figure>
