---
description: >-
  https://github.com/sqlparser/gsp_demo_java/tree/master/src/main/java/demos/dlineage#dataflowanalyzer
---

# Overview

* Support more than 20 major databases and still growing
* Build from scratch, no third-party library needed.
* Easy integration.
* Rich demo code to help you start quick

<figure><img src="../../.gitbook/assets/sqlflow_components.png" alt=""><figcaption></figcaption></figure>

## 以下内容感觉个人有疑问，先暂停一下

### DataFlowAnalyzer

Collects the end-to-end column-level data lineage in the Data Warehouses environment by analyzing SQL script especially stored procedure like PL/SQL.

This tool introduces a new data lineage model that is compatible with the Apache Atlas type system to describle the data flow of table/columns.

This tool is built from the scratch, it is the main part of the backend of [the SQLFlow Cloud](https://sqlflow.gudusoft.com).

### Releases

* \[Ver2.2.0, 2022/07/21] Use /env parameter to provide metadata.
* \[Ver2.1.2, 2021/07/13] Update readme, illustrates how to connect to database instance in command line.
* \[Ver2.1.1, 2021/07/12] Update download, data lineage model document.
* \[Ver2.1.0, 2021/07/11] Release gsp core 2.3.7.2

### Links

* [First version, 2017-8](https://github.com/sqlparser/wings/issues/494)
