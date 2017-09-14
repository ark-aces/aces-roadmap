# ACES Development Roadmap

## Phase 1. ACES Marketplace Platform

The ACES Marketplace is a consumer platform for blockchain services built around Ark. 

The main components of the platform are:

- Ark Listener Relay Nodes
- ACES Service Nodes
- ACES Marketplace Nodes
- ACES Marketplace Console


### Ark Listener Relay Node

The Ark Listener Relay Node runs as a web service that scans Ark transactions and posts data to registered service nodes. The intent of this service is to take the complexity of running an Ark transaction listener off the developers wanting to implement ACES services. The Ark Listener Relay Node provides a simple web service interface for registering a service and receiving callbacks when Ark transactions are made to the service Ark address.

Technical Requirements:
- Swagger API Definition
- Web service application (Spring Boot Web Service + PostgreSQL Database)
- Deployment tools (Vagrant)


### ACES Service Nodes

The ACES Service Nodes are developed and run by the ACES community. ACES defines a common web API protocol for services that developers must implement to be compatible with the ACES Marketplace. ACES Service Nodes can be written in any language by implementing the web service API. 

Technical Requirements:
- Swagger API Definition
- Developer Documentation
- Example Service Implementations


### ACES Marketplace Node

The ACES Marketplace Node tracks users and ACES Services. 

The ACES team will host and maintain a production instance of the ACES Marketplace Console, but anybody will be able to deploy and host their own marketplaces with distinct user-base and services.
This service provides a web API for registering ACES Service Nodes and consuming registered Service Nodes. It also tracks 

Key Features:
- Tracks basic statistics on Service availability and usage (such as number of executions, total value sent to service, number of failed executions, etc…)
- Allow users to report services. The marketplace admin may want to suspend services or remove them from the marketplace if they are found to be causing problems.
- Provides a search index for looking up services

Technical Requirements:
- Swagger API Definition
- Web service application (Spring Boot Web Service + PostgreSQL Database)
- Deployment tools (Vagrant)


### ACES Marketplace Console

The ACES Service Marketplace Console is the consumer side web application that allows users to log in and consume community run ACES Services. It provides a searchable directory of registered services and an execution environment for running services.

Key Features:
- Allow users to create an account and optionally generate a consumer wallet tied to their account.
- Allow users to pay for service contracts using their Ark Desktop Wallet or generate a wallet in the Marketplace under their account to automatically pay for services.
- Create a service admin interface that allows users to register, manage, and test their ACES Services


## Phase 2. ACES Service Capabilities

ACES Services can be developed and hosted by anybody, but the ACES team plans to implement a number of services to be added to the marketplace.


### Eth to Ark Transfer Service

Create an ACES Service to Transfer Eth to an Ark Wallet. The service will create an
Eth wallet and respond to transactions sent to it by creating a corresponding Ark
transaction to the recipient.


### Bitcoin Listener Relay Node

The Bitcoin Listener Relay Node works just like the Ark Listener Relay Node and implements the same web interface for registering and receiving posts for transactions on the Bitcoin blockchain.


### Formless Functions

Formless Functions allow users to execute ACES services directly from an Ark transaction by including specially formatted text into the SmartBridge data field. Example: Smartbridge text sent to a listener reading ‘Send 1 btc to 0x238h32f8h23f’ would be accepted.


### IPFS Listener Relay Node and IPFS Service

Provide an ACES Service implementation for uploading IPFS files.

