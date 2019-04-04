### Summary
Make current config server functionality as pluggable features so that clients can inject their own implementation of config server e.g. implementation that uses Spring config server

### Motivation
To open up light-4j so that clients can use their own config server implementation if required. 

A new ConfigServerStartupHookProvider can be created and current config server related code can be moved there. And then Server class will just call this code in start method when it triggers all the startup hook providers. This way, clients can write their own ConfigServerStartupHookProvider and override current implementation.

### Guide-level explanation
To use the new ConfigServerStartupHookProvider, it should be added to service.yml file as singleton so that singleton factory can keep its ready before Server can trigger its onStartup method. 

### Reference-level explanation


### Drawbacks


### Rationale and Alternatives


### Unresolved questions
