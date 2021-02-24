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
1. Main module
  1. Checking the software configuration
  2. Checking the hardware configuration
  3. Checking data configuration
  4. Data
