---
description: https://github.com/sqlparser/sqlflow_public/tree/master/api#prerequisites
---

# Prerequisites

This article describes how to use the Rest API provided by the SQLFlow to communicate with the SQLFlow server and get the generated metadata and data lineage.

In order to use the SQLFlow rest API, you may connect to the [**SQLFlow Cloud server**](https://sqlflow.gudusoft.com) or setup a [**SQLFlow on-premise version**](https://www.gudusoft.com/sqlflow-on-premise-version/) on your owner server.

### **SQLFlow Cloud server**

If you want to connect to [the SQLFlow Cloud Server](https://sqlflow.gudusoft.com), you may [request a 30 days premium account](https://www.gudusoft.com/request-a-premium-account/) to get the necessary userId and secret code.

Once getting the premium account, please click the icon at the right top of the screen:

<figure><img src="../.gitbook/assets/sqlflow_userid_secret_step1.png" alt=""><figcaption></figcaption></figure>

Click the `Account` menu item to see:

<figure><img src="../.gitbook/assets/sqlflow_userid_secret_step2.png" alt=""><figcaption></figcaption></figure>

Here you can

* Copy the userId
* By default, the Secret key field is empty, please click the `generate` button to create a new secret key and copy this code.

### **SQLFlow on-premise version**

Please [check here](../introduction/installation/) to see how to install SQLFlow on-premise version on you own server.

* User ID
* Secrete Key

Always set userId to `gudu|0123456789` and keep `userSecret` empty when connect to the SQLFlow on-premise version.

### Difference of the API calls between SQLFlow Cloud server and SQLFlow on-premise version

1. TOKEN is not needed in the API calls when connect to the SQLFlow on-premise version
2. userId alwyas set to `gudu|0123456789` and `userSecret` leave empty when connect to the SQLFlow on-premise version.
3. The server port is 8081 by default for the SQLFlow on-premise version, and There is no need to specify the port when connect to the SQLFlow Cloud server.

Regarding the server port of the SQLFlow on-premise version, please [check here](https://github.com/sqlparser/sqlflow\_public/tree/master/grabit#1-sqlflow-server) for more information.

