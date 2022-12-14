# Table of contents

## Introduction

* [What is Gudu SQLFlow?](README.md)
  * [What SQLFlow can do](introduction/what-is-gudu-sqlflow/what-sqlflow-can-do.md)
  * [How to use SQLFlow](introduction/what-is-gudu-sqlflow/how-to-use-sqlflow.md)
* [Getting Started](introduction/getting-started/README.md)
  * [Sign up a new account](introduction/getting-started/sign-up-a-new-account.md)
* [Installation](introduction/installation/README.md)
  * [Linux](introduction/installation/linux.md)
  * [MacOS](introduction/installation/macos.md)
  * [Windows](introduction/installation/windows.md)
* [UI](introduction/ui/README.md)
  * [SQLText Editor](introduction/ui/sqltext-editor.md)
  * [Settings](introduction/ui/settings.md)
  * [Job Management](introduction/ui/job-management.md)
  * [Schema](introduction/ui/schema.md)
* [Java Library](introduction/java-library/README.md)
  * [Overview](introduction/java-library/overview.md)
  * [Usage](introduction/java-library/usage.md)
    * [Analyze data linege from SQL files](introduction/java-library/analyze-data-linege-from-sql-files.md)
    * [Analyze data linege from a database](introduction/java-library/analyze-data-linege-from-a-database.md)
    * [Resolve the ambiguous columns in SQL query](introduction/java-library/usage/resolve-the-ambiguous-columns-in-sql-query.md)

## CONCEPTS

* [Data lineage](concepts/data-lineage/README.md)
  * [Dataflow](concepts/data-lineage/dataflow.md)
    * [Relations generated by SQLFlow](concepts/data-lineage/dataflow/relations-generated-by-sqlflow.md)
  * [Direct Dataflow](concepts/data-lineage/direct-dataflow.md)
  * [Indirect Dataflow](concepts/data-lineage/indirect-dataflow.md)
  * [Aggregate function and Dataflow](concepts/data-lineage/aggregate-function-and-dataflow.md)
  * [Dataflow chain](concepts/data-lineage/dataflow-chain.md)
  * [Data lineage format reference](concepts/data-lineage/data-lineage-format-reference.md)

## ARCHITECTURE

* [Overview](architecture/overview.md)

## API Docs

* [Prerequisites](api-docs/prerequisites.md)
* [Using the Rest API](api-docs/using-the-rest-api.md)
* [SQLFlow Rest API reference](api-docs/sqlflow-rest-api-reference/README.md)
  * [User Interface](api-docs/sqlflow-rest-api-reference/user-interface.md)
  * [Generation Interface](api-docs/sqlflow-rest-api-reference/generation-interface/README.md)
    * [/sqlflow/generation/sqlflow](api-docs/sqlflow-rest-api-reference/generation-interface/sqlflow-generation-sqlflow.md)
    * [/sqlflow/generation/sqlflow/exportLineageAsCsv](api-docs/sqlflow-rest-api-reference/generation-interface/sqlflow-generation-sqlflow-exportlineageascsv.md)
  * [Job Interface](api-docs/sqlflow-rest-api-reference/job-interface/README.md)
    * [/sqlflow/job/submitUserJob](api-docs/sqlflow-rest-api-reference/job-interface/sqlflow-job-submituserjob.md)
    * [/sqlflow/job/displayUserJobSummary](api-docs/sqlflow-rest-api-reference/job-interface/sqlflow-job-displayuserjobsummary.md)
    * [/sqlflow/job/displayUserJobsSummary](api-docs/sqlflow-rest-api-reference/job-interface/sqlflow-job-displayuserjobssummary.md)
    * [/sqlflow/job/exportLineageAsJson](api-docs/sqlflow-rest-api-reference/job-interface/sqlflow-job-exportlineageasjson.md)
    * [/sqlflow/job/exportFullLineageAsCsv](api-docs/sqlflow-rest-api-reference/job-interface/sqlflow-job-exportfulllineageascsv.md)
    * [/sqlflow/job/exportLineageAsGraphml](api-docs/sqlflow-rest-api-reference/job-interface/sqlflow-job-exportlineageasgraphml.md)
    * [/sqlflow/job/submitPersistJob](api-docs/sqlflow-rest-api-reference/job-interface/sqlflow-job-submitpersistjob.md)
* [Swagger UI](api-docs/swagger-ui.md)
* [Export the data lineage result](api-docs/export-the-data-lineage-result.md)

## SQLFlow Widget

* [Online Demo](sqlflow-widget/online-demo.md)
* [Get started](sqlflow-widget/get-started.md)
* [Instance API](sqlflow-widget/instance-api.md)
* [SQLFlow Widget](sqlflow-widget/sqlflow-widget.md)

## Databases

* [Database Objects](databases/database-objects/README.md)
  * [Azure](databases/azure.md)
  * [DB2](databases/db2.md)

## SQLFlow-ingester

* [Introduction](sqlflow-ingester/introduction.md)
* [Git Repo](sqlflow-ingester/git-repo.md)

## OTHER

* [FAQ](other/faq.md)
* [Roadmap](other/roadmap.md)
