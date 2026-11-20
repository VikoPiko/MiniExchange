# Vision document for MiniEx

1. Introduction
   1.1. Purpose
   The purpose of this document is to lay down the basis of what is to be a mini exchange system ("MiniEx"), define the scope, function and non-functional requirements and resources.
   1.2. Scope
   The scope of the following project is to build a mini exchange system that allows users to create accounts, which are paper funded (paper trades only), a ledger, API for interaction as well as CI/CD pipelines, Terraform and Helm configurations as well as Telemetry and a Message Broker.
   1.3 References
   "CLAUDE.md" as a direct reference, containing scope definitions, agent context and others.

2. Positioning
   2.1. Business opportunity
   Not applicable - This project is aimed for a solo-developer with the goal of improving coding skills and architecture. No real business value for external stakeholders or users, except potential test users of the system.
   2.2. Problem statement
   The problem addressed by this system is designing an end-to-end system from the grounds up, using no AI as a help (unless guidance and oversight are needed). The developer working on this system is usually messy and loses project motivation fast - The central aim of this system is addressing those issues by providing the opportunity and scope for a more focused and easy to stick to system.

3. Stakeholder and User description
   3.1. Stakeholder
   The developer in question:
   - Aims to regularly work and improve on this project
   - Is looking to test out Documentation abilities and Architecture design skills.

4. Product overview

The system will implement the following items:

- An execution engine
- A ledger for entries
- An API for HTTP(S) communication
- Telemetry tools for monitoring
- A message broker (for jobs/events in the distributed system)
- Deployment via K3s with Terraform and Helm configurations.

  4.1. Explicit scope definition
  The system will implement the following features:

- A trade execution engine
- A ledger for trade entries
- A TCP API for communication
- A message broker for communication between the systems
- Monitoring tools (Grafana, Prometheus, Loki)
- A browser dashboard

  4.2. The System will NOT implement:

- Real money trading, deposits or withdrawals.
- Third party connection integrations and tools.
- Third-party IdP providers (except potentially Keycloak)

1. Constraints and Quality ranges
   The constraints for the following system considering time and resources are:

- Weekly availability of 8-12hrs.
- No budget for the development (purely free and for educational purposes)
- Single developer working on requirements, documents, development, DevOps, testing and monitoring.

6. Main use cases:

- Create account
- Add funds
- Place order
- Cancel order
- Trade settles
- Engine crash and recovery
- Withdrawal
- Deposit (Simulated)

  6.1. Non-functional requirements:
  To be added...
