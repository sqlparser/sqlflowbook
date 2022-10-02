# SQLFlow Rest API reference

All the Restful requests are based on JWT authorization. Before accessing the sqlflow WebAPI, client user needs to obtain the corresponding JWT token for legal access. Each webapi contains two parameters, named userId and token. Check [here](../prerequisites.md) on how to pass through the authentification.

Basically, there are three parts of interface in SQLFlow Rest API:

* [User Interface](user-interface.md)
* [Generation Interface](generation-interface/)
* [Job Interface](job-interface/)
