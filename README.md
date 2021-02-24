# hello_world_golang
Hello world, golang!
### Diagram markdown
mermaid
graph TB; 
  CLI-->Main_module;
  NATS_server-->Request_module;
  Request_module-->NATS_server;
  subgraph NATS_client; 
    Main_module-->Configuration_module; 
    Configuration_module-->Stats_collection_module;
      Stats_collection_module-->Request_module;
      Request_module-->Data_processing_module;
      Data_processing_module-->Report_module;
end;

### System modules
1. Main module.
    1.1. Checking the software configuration.
    1.2. Checking the hardware configuration.
    1.3. Checking data configuration.
    1.4. Checking the correctness of the input data.
2. Configuration module.
    2.1. Contains all system settings "by default".
    2.2. Contains all rules and restrictions on testing parameters.
    2.3. Sends parameters to the system for testing.
3. Test request generation module
    3.1. Receives test configuration data.
    3.2. Opens a database for maintaining a test report.
    3.3. Launches the testing system, maintains a report in the database about the testing progress.
    3.4. After completing the task for the test, closes the database.
4. Statistics collection module.
    4.1. Receives test configuration data.
    4.2. Opens a database for maintaining a report on the responses of the remote server about testing.
    4.3. Keeps a report in the database on the progress of testing.
    4.4. After completing the task for the test, closes the database.
5. Module for processing statistical data
    5.1. Receives test configuration data.
    5.2. Open databases with records of requests to the server, BD with records of responses from the server.
    5.3. From the test configuration data, take the order of processing statistics.
    5.4. Generation of a report on the testing system.
