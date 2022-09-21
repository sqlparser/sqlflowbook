# SQLText Editor

Enter your SQL code in the live editor. You can choose the database under the section of dbvendor. Visualize your data lineage by clicking _`visualize`_ or _`visualize join`_.

<figure><img src="../../.gitbook/assets/185734862-10a41894-eeb8-4331-a25f-1c764ae0ebc0.gif" alt=""><figcaption></figcaption></figure>

When clicking _`visualize`_, we are using the following input paramaters to request the graph API:

| Parameter        | Value                                                              |
| ---------------- | ------------------------------------------------------------------ |
| sqltext          | SQL code in the left live editor, for example `select * from a;`   |
| dbvendor         | database selected under the dbvendor section such as _`dbvoracle`_ |
| showRelationType | fdd                                                                |
| ignoreFunction   | true                                                               |

When clicking _`visualize join`_, we are using the following input paramaters to request the graph API:

| Parameter        | Value                                                              |
| ---------------- | ------------------------------------------------------------------ |
| sqltext          | SQL code in the left live editor, for example `select * from a;`   |
| dbvendor         | database selected under the dbvendor section such as _`dbvoracle`_ |
| showRelationType | join                                                               |
| ignoreFunction   | true                                                               |

### Switch sample SQL

Click the dbvendor menu and select the database. Click sample _`SQL`_ to get the sample sql corresponding to this dbvendor in the live editing box.

<figure><img src="../../.gitbook/assets/185735004-847cdb63-88a4-49db-8482-8820920daded.gif" alt=""><figcaption></figcaption></figure>

### Visualize a column or table by dropdown menu

<figure><img src="../../.gitbook/assets/185736807-21bb3f70-3fb2-47d6-a97d-c910b139fcbc.gif" alt=""><figcaption></figcaption></figure>

### Hover sqltext to highlight graph

Hover over sqltext to find the corresponding graph.

<figure><img src="../../.gitbook/assets/185735065-d22debe6-6dbf-417d-9e61-798b28d9ddf6.gif" alt=""><figcaption></figcaption></figure>

### Hover graph to highlight sqltext

Hover over graph to find the corresponding sqltext.

<figure><img src="../../.gitbook/assets/185735156-de5d071a-1a55-4914-81a4-90aac85aa036.gif" alt=""><figcaption></figcaption></figure>

### Resize left panel width

Hover over the edge of the panel. You can drag and change the width when there is a highlight.

<figure><img src="../../.gitbook/assets/185735279-20b41fb1-a191-40fa-9fc1-d258246ea0fe.gif" alt=""><figcaption></figcaption></figure>

### Pin graph, drag graph, and cancel

Click a column in the graph to fix the upstream and downstream relationships. Press and hold down the left mouse button to move the canvas.

<figure><img src="../../.gitbook/assets/185735432-0ef385fd-b1b8-4269-ae47-e339e2b78bf5.gif" alt=""><figcaption></figcaption></figure>
