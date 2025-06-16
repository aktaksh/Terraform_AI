SOW XDS
SOW 1.1 : TAXI APIs
Objective:
XDS operates infrastructure across multiple cloud providers and hybrid environments, creating operational complexity through inconsistent provisioning patterns and provider-specific management approaches. TAXI APIs provide a unified semantic layer for infrastructure lifecycle management using standardized stack-based constructs that abstract provider implementations. The platform enables consistent provisioning, configuration, and governance across multi-cloud environments through platform-agnostic API contracts, reducing manual intervention while maintaining operational consistency and establishing foundational capabilities for automated infrastructure management.

Activities:

**Design Phase:**
- **Domain Modelling:**
- Define core concepts and semantics (e.g., Infrastructure Stack, Workload, Environment, Run, Product)
- L1 Public Cloud Product Catalogs & SKUs – GCP / Azure / AWS LZs
- L2 Public Cloud Product Catalogs & SKUs – GKE / Vertex AI, etc.
- L1 Private Cloud Product Catalog & SKUs – RedHat VMs
- L2 Private Cloud Product Catalog & SKUs – RedHat OpenShift NS
- Identify bounded contexts and segregate subdomains (e.g., Provisioning, Deployment, Monitoring)
- Model entities, value objects, and aggregates
- Identify a list of domain events (e.g., Stack Provisioned, Run Completed)
- Capture workflows and state transitions (e.g., Stack lifecycle: Draft → Provisioning → Active → Deprecated)
- Design ubiquitous language across code, schema, and APIs
- Partition domain logic into domain services, entities, and factories
- Validate model with domain experts and iterate on design
- Document domain glossary and conceptual model for shared understanding

- **Relational Schema Modelling:**
- Model core entities – Workloads, Env, Stack, Workflows, Runs, Product, etc.
- Establish relationships and cardinality
- Define attributes, derived attributes, and constraints
- Normalize schema and data models
- Model lifecycle metadata (created_at, updated_at, versioning, soft-delete flags for auditability)
- Validate domain semantics – review entity boundaries, cardinality, and constraints with stakeholders

- **API Contract Design:**
- Design API schemas and models
- Design URI structure and resource hierarchy
- Map CRUD operations to HTTP verbs
- Define request/response payloads and schemas
- Establish resource linking and nesting strategies
- Add filtering, sorting, pagination support
- Define standard status codes and error formats
- Model idempotency and optimistic concurrency
- Implement authentication and authorization layers
- Define API versioning strategy
- Document with OpenAPI/Swagger
- Test API contracts
- Integrate into CI/CD with linting and schema validation
- Design webhook/event streaming for real-time workflow integrations

**Implementation Phase:**	
- Choose backend framework (e.g., NestJS, Fastify, Express) in TypeScript
- Scaffold project structure with modular, domain-driven design
- Implement RDBMS entities using ORM (e.g., Prisma, TypeORM)
- Map API contracts to controllers, services, and DTOs
- Enforce validation, serialization, and error handling
- Wire business logic with service layer abstractions
- Configure DB migrations, seed data, and schema versioning
- Implement authentication and RBAC using middleware/guards
- Integrate logging, tracing, and structured error reporting
- Set up unit, integration, and contract tests with coverage enforcement
- Integrate linting, static analysis, and code quality gates (e.g., ESLint)
- Configure CI/CD pipelines for build, test, and deploy
- Use containerization and define infra-as-code for environments
- Automated API documentation generation and publishing
- Enable observability with metrics, health checks, and alerts

**Security Hardening Phase:**
- In alignment with the NIST Secure Software Development Framework (SSDF), the following activities will be performed to integrate security throughout the software development lifecycle:
- Early Threat and Vulnerability Detection: Proactively identify and mitigate threats and vulnerabilities during the early stages of the SDLC to support secure design and reduce downstream risk
- Threat Modeling: Conduct structured threat modeling exercises to analyze system components, data flows, and trust boundaries—identifying high-risk and commonly exploitable vulnerabilities early in the design process
- Security-Focused Design and Architecture Reviews: Perform detailed security reviews of system and software architecture to ensure that designs meet defined security objectives and reduce the attack surface
- Static Code Analysis: Use automated static analysis tools to detect insecure coding practices, input validation issues, and common vulnerability patterns, in line with NIST-recommended secure coding standards
- Security Requirements Definition: Define and document explicit, testable security requirements—including authentication, authorization, data protection, and error handling—based on NIST and application-specific guidance
- Collaborative Peer Code Reviews: Facilitate structured peer reviews of source code with a focus on identifying security flaws, enforcing secure coding standards, and promoting team accountability
- Threat Intelligence & CVE Prioritization (RV.1.3): Integrate up-to-date threat intelligence feeds and prioritized Common Vulnerabilities and Exposures (CVEs) into development workflows to continuously assess and manage security risks
- Cost-Efficient Risk Mitigation: Optimize testing and remediation efforts by targeting high-impact vulnerabilities and preventing costly recoding or security incidents post-deployment

**Backlog and Continued Development of API platform**

- Performance & Scalability: API benchmarking, load testing, capacity planning, and auto-scaling strategy
- Operations and SRE: Disaster recovery design, operational runbooks, incident response procedures, and monitoring dashboards
- API Governance: Rate limiting, lifecycle management, versioning strategy. 
- Integration & Testing: End-to-end testing, chaos engineering, and contract testing for API consumers
- Define other key areas of focus to improve the feature set and technical architecture of the API platform. 


Outcomes: 

-	- Reduce infrastructure provisioning time across multi-cloud environments through standardized TAXI API workflows.
-	- Eliminate tooling and process complexity by implementing unified API contracts for infrastructure provisioning across CSPs and on-premises environments.
-	- Accelerate infrastructure onboarding via a standardized domain model and shared platform language.
-	- Achieve NIST SSDF compliance with integrated security practices, reducing security vulnerabilities reaching production.
-	


Deliverables:
-	- Domain Architecture Documentation in Confluence or PDF, including entity relationship diagrams
-	- Database Schema Package with normalized relational schema and data dictionary documentation
-	- API Specification Documentation (OpenAPI/Swagger) with complete REST API contracts
-	- TAXI Platform Source Code in TypeScript with production-ready backend implementation 
-	- Containerized deployment configurations and CI/CD pipeline definitions
-	- Security Assessment Reports in PDF with threat modeling analysis, static code analysis results, and remediation recommendations
-	- Operational Documentation Package including developer onboarding guides, troubleshooting runbooks, and architectural decision records
-	

Assumptions: 

- The technical design for domains, events, ER diagrams, REST API contracts will be developed in collaboration and approved by XDS stakeholders
- Architecture and tooling choices will evolve as the design progresses and implemented in an agile and iterative fashion
- Procurement of tools and platforms that the architecture will depend on to be managed by XDS stakeholders and made available in a timely manner to meet objectives
- The programming language to be used across the stack will be typescript
- XDS team will support the development activities by adding capacity to the core squad
- TAXI APIs will be treated as a product and follow agile SDLC principles
- Necessary security tools must be integrated with XDS environments for vulnerability detection and threat intelligence
- Development and security teams will be available for joint working sessions, including threat modeling workshops and peer code reviews

Out of Scope: 

- Security tool procurement is out of scope of this engagement
- Remediation of vulnerabilities or architectural redesigns identified during threat modeling, code reviews, or static analysis (recommendations will be provided, but implementation is not included)
- Penetration testing or red teaming activities; these are separate exercises and not part of this security hardening engagement
- Security testing of third-party components, libraries, or systems not under direct control of the client’s development team





