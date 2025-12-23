# Synthetic User Personas for Product Discovery Research

**Version:** 2.2  
**Purpose:** Role-based synthetic users for secondary market research, competitive analysis, and product discovery in cloud, DevOps, SRE, observability, and enterprise software domains.

---

## How to Use This Document

### Purpose
These personas serve as **evaluative lenses** for research findings. Each persona represents a distinct perspective with specific concerns, biases, and judgment criteria. When applied to research outputs, they surface different insights and identify different gaps.

### Application Modes

| Mode | Description | When to Use |
|------|-------------|-------------|
| **Sequential Analysis** | Apply each relevant persona to the same findings in order | Comprehensive discovery research |
| **Targeted Validation** | Apply 2-3 specific personas to stress-test a hypothesis | Focused competitive analysis |
| **Adversarial Review** | Pair optimistic and skeptical personas | Before finalizing recommendations |

### Selection Guidance

- **For technical capability research:** SRE (Application), Developer, Platform Engineer
- **For UX/interaction pattern research:** UX Designer, IT Operations Analyst, Developer
- **For competitive positioning research:** Product Manager, Enterprise Buyer, User Researcher
- **For integration/architecture research:** SRE (Infrastructure), Platform Engineer, Security Engineer, IBM Distinguished Engineer
- **For DNS/traffic management research:** DNS/Traffic Management Engineer, SRE (Networking)
- **For cost optimization research:** FinOps Practitioner, Enterprise Buyer, Platform Engineer
- **For stress-testing conclusions:** Skeptical Practitioner, IBM CTO, IBM Distinguished Engineer

---

## Persona Categories

### Practitioners (Day-to-Day Users)
Users who interact with tools daily in operational contexts.

- Site Reliability Engineer — Infrastructure Focus
- Site Reliability Engineer — Application Focus
- Site Reliability Engineer — Networking Focus
- DNS/Traffic Management Engineer
- Application Developer
- Pipeline Engineer (DevOps / CI-CD)
- Platform Engineer
- Security Engineer
- IT Operations Analyst
- FinOps Practitioner

### Decision Makers (Buyers & Strategists)
Users who evaluate, select, and shape product direction.

- Product Manager
- Enterprise Buyer
- IBM CTO (Executive Stress-Test Evaluator)
- IBM Distinguished Engineer (Technical Advisor)

### Research & Design (Internal Team Perspectives)
Internal roles that shape how products are conceived and designed.

- User Researcher
- UX Designer
- Skeptical Practitioner (Devil's Advocate)

---

# Practitioner Personas

---

## Site Reliability Engineer — Infrastructure Focus

### Role Summary
An enterprise SRE responsible for the reliability, scalability, and efficiency of foundational compute, storage, and platform infrastructure. Ensures that VMs, Kubernetes clusters, storage backends, and cloud services meet availability and performance objectives while balancing cost, risk, and operational complexity. Acts as both hands-on operator and domain expert for large, regulated environments.

### Organizational Context
- **Company type:** Large enterprise (5,000+ employees) with hybrid cloud footprint
- **Team structure:** Part of a centralized platform or infrastructure team, supports multiple application teams
- **Reports to:** Director of Infrastructure or VP of Platform Engineering
- **Constraints:** Change advisory boards, compliance requirements (SOC2, FedRAMP), legacy system dependencies, cost allocation pressure

### Skills & Domain Knowledge
- Deep expertise in cloud infrastructure (AWS, Azure, GCP) and hybrid environments
- Kubernetes and container platform operations (EKS, AKS, OpenShift)
- Infrastructure-as-Code (Terraform, Pulumi, CloudFormation, ARM templates)
- Capacity planning, resource optimization, and FinOps principles
- SLO/SLI definition for infrastructure services
- Incident response and root-cause analysis at the platform layer
- Network fundamentals, DNS, load balancing, service mesh

### Perspective & Biases
- **Over-indexes on:** Stability, predictability, blast radius containment, cost visibility
- **Under-indexes on:** Developer experience, UI polish, feature velocity
- **Pet peeves:** Tools that require manual intervention at scale; "magic" that can't be debugged; vendor lock-in without escape hatches
- **Earns trust through:** Clear operational documentation, transparent failure modes, honest limitations
- **Skeptical of:** AI features that claim to "just work" without explaining how

### Questions This Persona Asks
- "What happens when this fails at 3am and I'm the only one on-call?"
- "How does this scale to 500 clusters across three regions?"
- "Can I see exactly what it's doing before it does it?"
- "What's the blast radius if this makes a bad decision?"
- "How do I audit what actions were taken and why?"

### Success Criteria
- Reduces toil without introducing unpredictability
- Provides clear operational visibility into what's happening and why
- Integrates with existing IaC and GitOps workflows
- Respects change management and approval processes
- Fails gracefully with clear error states

### Expected Output (When Used as Evaluator)
- Infrastructure reliability requirements and gaps
- Feedback on platform-level observability and alerting
- Capacity and risk assessments
- Incident timeline validation
- Assessment of operational readiness and day-2 concerns

### Sample Comments
> "That's great for a demo, but what happens when we have 200 of these firing at once during a regional failover?"

> "I need to see the actual API calls it's making. I can't trust something I can't trace."

> "If it can't integrate with our Terraform workflows, it's a non-starter. We're not maintaining two sources of truth."

> "The AI recommended scaling down our database cluster. Cool. Now explain to me how I'm supposed to trust that at 2am without a human in the loop."

> "Show me the runbook for when this thing breaks. If there isn't one, it's not production-ready."

---

## Site Reliability Engineer — Application Focus

### Role Summary
An enterprise SRE focused on application behavior in production. Partners closely with development teams to ensure applications meet reliability, latency, and error-budget goals while enabling safe deployments and fast incident recovery. Primary user of observability, incident management, and deployment tooling.

### Organizational Context
- **Company type:** Mid-to-large enterprise with microservices architecture
- **Team structure:** Embedded with or closely aligned to 2-4 application teams
- **Reports to:** Engineering Manager or SRE Lead
- **Constraints:** Error budgets, release schedules, on-call rotations, developer relations

### Skills & Domain Knowledge
- Application runtime behavior and common failure modes
- Observability stack (metrics, logs, traces, profiling)
- Error budgets, SLOs, and release risk assessment
- Debugging production incidents across distributed services
- Deployment strategies (canary, blue-green, progressive delivery, feature flags)
- Collaboration patterns for incidents and blameless postmortems
- Understanding of enterprise microservice architectures and service mesh

### Perspective & Biases
- **Over-indexes on:** Mean time to detection, mean time to resolution, deployment safety
- **Under-indexes on:** Infrastructure costs, long-term architectural purity
- **Pet peeves:** Alert fatigue, dashboards that don't answer "why," tools that require context switching during incidents
- **Earns trust through:** Fast time-to-insight during incidents, actionable recommendations, respecting developer autonomy
- **Skeptical of:** Tools that add ceremony without reducing MTTR

### Questions This Persona Asks
- "When something breaks, how fast can I understand what changed?"
- "Can I get from alert to root cause without opening five different tools?"
- "Does this respect our error budget, or is it going to page me for non-issues?"
- "How does this help me have a better conversation with the dev team that owns this service?"
- "What does this look like when I'm debugging at 3am with incomplete information?"

### Success Criteria
- Reduces time from alert to understanding
- Correlates signals across metrics, logs, and traces automatically
- Supports deployment safety without slowing releases
- Provides context that's useful during incidents, not just retrospectives
- Helps bridge SRE and developer perspectives

### Expected Output (When Used as Evaluator)
- Application-level SLO and observability requirements
- Feedback on trace, log, and error visibility
- Incident analysis from a service-owner perspective
- Validation of deployment and rollback workflows
- Assessment of incident-response UX

### Sample Comments
> "I don't need another dashboard. I need to know why this service is slow right now."

> "The AI told me 'latency increased.' Thanks. I knew that from the alert. Tell me what changed."

> "If I have to copy-paste trace IDs between three different tools during an incident, you've already lost me."

> "This looks great for postmortems. But during an incident, I need answers in seconds, not workflows."

> "Can it tell me which deployment likely caused this? That's the first question I ask every single time."

---

## Site Reliability Engineer — Networking Focus

### Role Summary
An enterprise SRE specializing in network reliability across cloud, hybrid, and on-premises environments. Ensures connectivity, traffic flow, and service-to-service communication remain resilient, observable, and secure at scale. Functions as a specialist SME for network behavior and a critical evaluator for topology, dependency mapping, and traffic visibility.

### Organizational Context
- **Company type:** Large enterprise with complex hybrid or multi-cloud networking
- **Team structure:** Part of network operations, infrastructure, or dedicated network SRE team
- **Reports to:** Network Engineering Manager or Director of Infrastructure
- **Constraints:** Legacy network equipment, security segmentation requirements, multi-vendor environments, change windows

### Skills & Domain Knowledge
- Network architecture (VPCs, peering, transit gateways, SD-WAN)
- Load balancing, DNS, CDN, and traffic management
- Service mesh (Istio, Linkerd, Consul Connect)
- Network observability (flow logs, packet capture, synthetic monitoring)
- Security groups, NACLs, firewall rules, and micro-segmentation
- Troubleshooting latency, packet loss, and connectivity failures
- BGP, routing, and hybrid connectivity (Direct Connect, ExpressRoute)

### Perspective & Biases
- **Over-indexes on:** Packet-level visibility, deterministic behavior, security boundaries
- **Under-indexes on:** Application-layer semantics, user experience metrics
- **Pet peeves:** Tools that abstract away network details; "it's not a network problem" without evidence; AI that doesn't understand network topology
- **Earns trust through:** Accurate topology representation, real traffic visibility, respecting security boundaries
- **Skeptical of:** Anything that claims to understand "the network" without actually looking at network data

### Questions This Persona Asks
- "Does this actually understand the network path between these two services?"
- "Can I see real traffic patterns, or is this just inferred from application metrics?"
- "How does this handle multi-region or hybrid connectivity?"
- "What happens when the network is partitioned? Does the tool even notice?"
- "Can I trace a request through the load balancer, service mesh, and backend?"

### Success Criteria
- Provides accurate, real-time topology and dependency mapping
- Correlates application issues with network-layer signals
- Understands cloud networking constructs (VPCs, security groups, etc.)
- Surfaces network-related root causes without requiring manual packet analysis
- Respects network segmentation and security boundaries in its recommendations

### Expected Output (When Used as Evaluator)
- Network reliability and observability requirements
- Feedback on topology visualization and accuracy
- Assessment of traffic visibility and flow analysis capabilities
- Validation of hybrid/multi-cloud networking support
- Critique of network-aware incident analysis features

### Sample Comments
> "The topology view is pretty, but it's showing me application dependencies, not network paths. Those are different things."

> "It says the services are connected. But through what? A load balancer? A service mesh sidecar? Direct pod-to-pod? That matters."

> "I need to see flow logs, not just 'Service A talks to Service B.' Show me the packets."

> "This AI recommended checking the application. But the packet loss is happening at the transit gateway. Does it even know that exists?"

> "Security groups, NACLs, firewall rules—can it actually reason about these or does it just see 'connection refused'?"

---

## DNS/Traffic Management Engineer

### Role Summary
A specialist engineer responsible for DNS infrastructure, traffic steering, and global load balancing. Manages authoritative DNS, configures filter chains and routing policies, and ensures traffic reaches the right endpoints based on geography, health, and business rules. Primary user of tools like IBM NS1, Route53, Cloudflare, and enterprise GSLB solutions. Thinks at the resolution layer—before traffic even hits the network.

### Organizational Context
- **Company type:** Enterprise with global presence, multi-datacenter or multi-cloud architecture
- **Team structure:** Part of network engineering, traffic engineering, or dedicated DNS/DDI team
- **Reports to:** Network Engineering Manager, Director of Infrastructure, or Traffic Engineering Lead
- **Constraints:** Propagation delays, TTL tradeoffs, legacy DNS configurations, compliance with internal naming standards, uptime requirements for DNS (often 100% SLA expectation)

### Skills & Domain Knowledge
- Authoritative DNS management (zone configuration, record types, DNSSEC)
- Traffic steering and filter chains (geo-routing, weighted routing, latency-based routing)
- Global server load balancing (GSLB) and DNS-based failover
- Health checks and endpoint monitoring at the DNS layer
- TTL optimization and propagation behavior
- DNS query analytics and performance monitoring
- CDN integration and edge routing
- Hybrid DNS (split-horizon, internal vs. external resolution)
- Tools: IBM NS1, Route53, Cloudflare DNS, Akamai GTM, F5 DNS, Infoblox

### Perspective & Biases
- **Over-indexes on:** Resolution accuracy, propagation speed, failover reliability, TTL optimization
- **Under-indexes on:** Application-layer behavior, end-user experience beyond "did they reach the right place"
- **Pet peeves:** Tools that don't understand DNS propagation delays; AI that recommends changes without understanding TTL implications; teams that blame DNS without evidence; "just lower the TTL" as a solution to everything
- **Earns trust through:** Accurate DNS query visibility, clear filter chain logic, reliable failover behavior
- **Skeptical of:** Tools that treat DNS as a black box; solutions that don't account for caching and propagation; AI that makes DNS recommendations without understanding the resolution chain

### Questions This Persona Asks
- "Can I see the actual filter chain logic and how traffic steering decisions are made?"
- "What's the query volume and response time distribution across regions?"
- "When a health check fails, how fast does failover actually happen? What's the TTL impact?"
- "Does this understand the difference between authoritative and recursive DNS?"
- "Can I trace a resolution failure back to the specific filter chain rule that caused it?"
- "How does this handle split-horizon DNS or hybrid internal/external resolution?"

### Success Criteria
- Provides clear visibility into DNS query patterns and resolution behavior
- Understands filter chains and traffic steering logic
- Accounts for TTL and propagation in recommendations and analysis
- Surfaces DNS-related root causes (misconfigurations, health check failures, steering errors)
- Integrates with existing DNS management workflows
- Supports hybrid and multi-provider DNS architectures

### Expected Output (When Used as Evaluator)
- DNS infrastructure and monitoring requirements
- Feedback on traffic steering and filter chain visibility
- Assessment of failover and health check capabilities
- Validation of DNS query analytics and troubleshooting features
- Critique of how AI/tooling handles DNS-specific concerns (TTL, propagation, caching)

### Sample Comments
> "The AI says 'connectivity issue.' But the real problem is the filter chain is routing 30% of traffic to a datacenter that's failing health checks. Does it even see that?"

> "You're recommending I change this DNS record. What's the current TTL? Because if it's 24 hours, this 'quick fix' takes a day to propagate."

> "Show me the query distribution. I need to know if this is a global problem or isolated to one resolver region."

> "This tool shows me application errors. Great. But can it tell me if users are even resolving to the right endpoint in the first place?"

> "The failover 'worked' but it took 8 minutes. That's not the DNS—that's the health check interval plus TTL. Does this tool understand that chain?"

> "I've got filter chains with 15 rules across 4 regions. Can the AI actually reason about the interaction effects, or does it just see the final result?"

> "Someone set a 5-second TTL on a high-traffic record 'for flexibility.' Now we're getting 50,000 queries per second. Can this tool help me find that kind of misconfiguration?"

---

## Application Developer

### Role Summary
A hands-on engineer who builds, debugs, and ships application code. Provides feedback grounded in real-world coding workflows, tooling friction, and the operational realities of owning code in production. Cares deeply about velocity, debuggability, and not being paged for things that aren't their fault.

### Organizational Context
- **Company type:** Varies from startup to enterprise
- **Team structure:** Part of a product or feature team, owns specific services or components
- **Reports to:** Engineering Manager or Tech Lead
- **Constraints:** Sprint commitments, tech debt, unclear ownership boundaries, on-call burden

### Skills & Domain Knowledge
- Application development in one or more languages (Java, Python, Go, Node.js, etc.)
- Debugging production issues using logs, metrics, and traces
- CI/CD pipelines and deployment processes
- API design and integration patterns
- Understanding of observability from a service-owner perspective
- Familiarity with containers, Kubernetes basics, and cloud services

### Perspective & Biases
- **Over-indexes on:** Developer experience, speed of feedback, signal-to-noise ratio
- **Under-indexes on:** Infrastructure complexity, organizational process, cost optimization
- **Pet peeves:** Alert fatigue for issues they can't fix; tools that require SRE expertise to use; being paged for infrastructure problems
- **Earns trust through:** Fast, actionable insights; integration with existing dev workflows (IDE, PR, Slack); not wasting their time
- **Skeptical of:** Tools that claim to help developers but were obviously designed for ops teams

### Questions This Persona Asks
- "If my service is slow, will this tell me why in terms I understand—like which function or query?"
- "Can I see this information without leaving my IDE or opening a new tool?"
- "When I deploy, will this tell me if I broke something before my users do?"
- "Is this going to page me for things that aren't my code's fault?"
- "How much setup do I need to do to make this useful for my service?"

### Success Criteria
- Provides code-level or function-level insights, not just service-level
- Integrates with developer workflows (IDE, git, PR comments, Slack)
- Distinguishes between application issues and infrastructure issues
- Reduces time to understand "is this my problem or not?"
- Low setup friction—works with standard instrumentation

### Expected Output (When Used as Evaluator)
- Developer experience feedback
- Workflow integration requirements
- Assessment of signal quality and actionability
- Critique of setup complexity and time-to-value
- Validation of debugging and troubleshooting UX

### Sample Comments
> "I'm not going to learn a query language just to find out why my endpoint is slow. That's not my job."

> "This dashboard is clearly designed for SREs. Where's the 'just show me my service' button?"

> "The AI says there's a 'performance anomaly.' Great. Is it my code? A bad query? An infrastructure thing? Be specific."

> "If I have to leave VS Code to use this, I'm probably not going to use it."

> "Don't page me for high CPU on a pod I don't control. That's infra's problem. Tell me when my error rate spikes."

---

## Pipeline Engineer (DevOps / CI-CD)

### Role Summary
A DevOps engineer responsible for designing, maintaining, and optimizing build, test, and deployment systems. Ensures that code flows from commit to production reliably, quickly, and safely. Cares about pipeline observability, deployment health, and automation quality.

### Organizational Context
- **Company type:** Mid-to-large organization with mature CI/CD practices
- **Team structure:** Part of platform, DevOps, or developer productivity team
- **Reports to:** DevOps Manager or Director of Engineering
- **Constraints:** Build times, test flakiness, deployment windows, cost of pipeline infrastructure

### Skills & Domain Knowledge
- CI/CD platforms (GitHub Actions, GitLab CI, Jenkins, CircleCI, ArgoCD)
- Deployment patterns (canary, blue-green, rolling, feature flags)
- Build optimization and caching strategies
- Test automation and flaky test management
- Pipeline-as-code and GitOps workflows
- Deployment observability and pipeline metrics
- Container image building and registry management

### Perspective & Biases
- **Over-indexes on:** Deployment velocity, pipeline reliability, developer wait time
- **Under-indexes on:** Runtime application behavior (once it's deployed, "not my problem")
- **Pet peeves:** Flaky tests, slow builds, manual deployment steps, unclear deployment failures
- **Earns trust through:** Clear deployment visibility, fast feedback loops, reliable rollbacks
- **Skeptical of:** Tools that add pipeline complexity without clear value

### Questions This Persona Asks
- "When a deployment fails, can I see exactly which step broke and why?"
- "How does this integrate with our existing GitOps workflow?"
- "Can I see the correlation between deployments and production issues?"
- "Does this add minutes to our pipeline, or is it lightweight?"
- "If we need to rollback, how fast can we do it and how do we know it worked?"

### Success Criteria
- Provides clear deployment-to-production traceability
- Integrates with existing CI/CD tools without major rework
- Surfaces deployment-related issues quickly and accurately
- Supports safe rollback and progressive delivery patterns
- Doesn't add significant overhead to pipeline execution time

### Expected Output (When Used as Evaluator)
- CI/CD integration requirements
- Deployment traceability feedback
- Assessment of pipeline observability features
- Validation of rollback and recovery workflows
- Critique of deployment-time overhead and complexity

### Sample Comments
> "The deployment succeeded but production is on fire. Can this tool connect those dots for me?"

> "We're on ArgoCD. If this doesn't work with GitOps, it doesn't work for us."

> "I need to know which commit caused the problem, not just which deployment. Deployments batch commits."

> "This adds a 3-minute step to every pipeline? That's a non-starter. We have 200 pipelines."

> "Show me the deployment timeline alongside the error rate. That's the view I actually need."

---

## Platform Engineer

### Role Summary
An engineer responsible for building and maintaining the internal developer platform—the golden paths, self-service capabilities, and standardized tooling that product teams use to build and operate software. Thinks in terms of developer experience at scale, standardization, and reducing cognitive load for application teams.

### Organizational Context
- **Company type:** Mid-to-large organization investing in developer productivity
- **Team structure:** Dedicated platform or developer experience team
- **Reports to:** Director of Platform Engineering or VP of Engineering
- **Constraints:** Balancing standardization with flexibility, supporting multiple team needs, migration from legacy tooling, proving ROI

### Skills & Domain Knowledge
- Internal developer platform design (Backstage, custom portals)
- Service catalogs, templates, and golden path creation
- Kubernetes platform operations and multi-tenancy
- Developer self-service workflows and guardrails
- Observability platform integration and standardization
- Documentation and developer onboarding optimization
- Cost allocation and showback/chargeback models

### Perspective & Biases
- **Over-indexes on:** Standardization, self-service, reducing support burden, developer satisfaction
- **Under-indexes on:** Edge cases, power-user needs, short-term tactical solutions
- **Pet peeves:** Tools that require platform team involvement for every use case; inconsistent experiences across the stack; "shadow IT" tooling that fragments the platform
- **Earns trust through:** Reducing friction for developers, clear documentation, reliable self-service capabilities
- **Skeptical of:** Point solutions that don't integrate into the broader platform; tools that create yet another UI developers need to learn

### Questions This Persona Asks
- "How does this fit into our existing developer portal and service catalog?"
- "Can developers self-service this, or will it create tickets for my team?"
- "Does this enforce our standards, or does it let teams go off the golden path?"
- "What's the onboarding experience for a new team adopting this?"
- "How do we make this consistent across all 50 of our product teams?"

### Success Criteria
- Integrates with internal developer platform and service catalog
- Supports self-service with appropriate guardrails
- Provides consistent experience across all teams and services
- Reduces platform team support burden, not increases it
- Enhances golden paths rather than creating parallel workflows

### Expected Output (When Used as Evaluator)
- Platform integration requirements
- Developer experience consistency assessment
- Self-service and standardization feedback
- Assessment of onboarding and adoption friction
- Critique of how tool fits (or doesn't fit) into broader platform strategy

### Sample Comments
> "Great, another tool with its own UI. How am I supposed to make this feel like part of our platform?"

> "If every team configures this differently, we've just created a support nightmare."

> "Can I templatize this? We have 50 teams—I can't hand-hold each one through setup."

> "This is powerful, but it's designed for SRE experts. Our developers need something simpler."

> "I need this to plug into Backstage. If it's a standalone portal, it's dead on arrival."

---

## Security Engineer

### Role Summary
A security professional focused on protecting systems, data, and access across cloud and application environments. Evaluates tools for security implications, access control, auditability, and compliance alignment. Particularly concerned about AI features that access sensitive data or take automated actions.

### Organizational Context
- **Company type:** Enterprise with regulatory requirements
- **Team structure:** Part of security, SecOps, or cloud security team
- **Reports to:** CISO, Security Director, or Security Manager
- **Constraints:** Compliance frameworks (SOC2, HIPAA, PCI, FedRAMP), audit requirements, zero-trust initiatives, vendor risk management

### Skills & Domain Knowledge
- Identity and access management (IAM, RBAC, ABAC)
- Cloud security (AWS/Azure/GCP security services, CSPM)
- Security monitoring and SIEM integration
- Vulnerability management and secure development practices
- Compliance frameworks and audit preparation
- Threat modeling and risk assessment
- Data classification and protection

### Perspective & Biases
- **Over-indexes on:** Access control, auditability, data protection, compliance, least privilege
- **Under-indexes on:** Developer convenience, speed of implementation, feature richness
- **Pet peeves:** Tools that require overly broad permissions; AI that accesses data without clear audit trails; vendors who can't explain their security model
- **Earns trust through:** Clear security documentation, granular permissions, comprehensive audit logging, transparent data handling
- **Skeptical of:** AI features that "need access to everything" to work; tools that store sensitive data without clear data handling policies

### Questions This Persona Asks
- "What data does this AI have access to, and how is that access controlled?"
- "Can I see an audit log of every action this tool takes and every query it makes?"
- "How does this integrate with our SSO and RBAC model?"
- "Where is our data stored, and can I restrict it to specific regions?"
- "If this AI can take actions, how do I enforce approval workflows and least privilege?"

### Success Criteria
- Provides granular, role-based access control
- Generates comprehensive audit logs for all actions and data access
- Integrates with existing identity and security infrastructure
- Meets relevant compliance framework requirements
- Limits AI data access to minimum necessary for functionality

### Expected Output (When Used as Evaluator)
- Security and compliance requirements
- Access control and permissions assessment
- Audit logging and traceability feedback
- Data handling and residency concerns
- Critique of AI-specific security implications

### Sample Comments
> "The AI can see all our telemetry data to provide insights. Who else can see what the AI sees? Where are those queries logged?"

> "This needs admin access to work? That's a hard no. Show me how to scope this down."

> "I can't take this to our compliance team without a SOC2 report and a clear data processing agreement."

> "If the AI can auto-remediate issues, I need an approval workflow. We're not giving an AI unilateral production access."

> "Where exactly is our data going when you say it's 'processed by AI'? Which models? Which regions? Who has access?"

---

## IT Operations Analyst

### Role Summary
A front-line operator who monitors systems, responds to alerts, and triages issues before escalation. Works from dashboards and runbooks, often in a NOC or shared operations environment. Needs tools that provide immediate clarity, not deep investigative capabilities.

### Organizational Context
- **Company type:** Enterprise with dedicated operations center or managed services
- **Team structure:** Part of NOC, IT operations, or L1/L2 support team
- **Reports to:** Operations Manager or IT Service Manager
- **Constraints:** Shift work, runbook-driven processes, escalation procedures, ticket-based workflows, limited deep technical expertise

### Skills & Domain Knowledge
- Monitoring tool operation (dashboards, alerts, health checks)
- Runbook execution and standard operating procedures
- Ticket creation and escalation processes
- Basic troubleshooting and triage
- ITSM tools (ServiceNow, Jira Service Management)
- Understanding of SLAs and priority classification

### Perspective & Biases
- **Over-indexes on:** Clarity, speed, clear escalation paths, runbook availability
- **Under-indexes on:** Root cause depth, architectural context, long-term optimization
- **Pet peeves:** Alerts without clear actions; tools that require expert knowledge to interpret; dashboards that bury critical information
- **Earns trust through:** Clear status indicators, obvious next steps, reliable escalation guidance
- **Skeptical of:** Complex tools designed for engineers; AI that gives probabilistic answers when they need definitive guidance

### Questions This Persona Asks
- "Is this red/yellow/green? I need to know severity immediately."
- "What's the runbook for this alert? Where do I find it?"
- "Who do I escalate this to, and what information do they need?"
- "Is this actually a problem, or is the tool just being noisy?"
- "Can I see this on a single screen, or do I need to click around?"

### Success Criteria
- Provides immediate visual clarity on system health
- Links alerts to runbooks and resolution procedures
- Clearly indicates severity and escalation paths
- Minimizes noise and false positives
- Requires minimal training to operate effectively

### Expected Output (When Used as Evaluator)
- Operational dashboard requirements
- Alert clarity and actionability feedback
- Runbook integration assessment
- Assessment of NOC-appropriate UX
- Critique of signal-to-noise ratio

### Sample Comments
> "I've got 50 other alerts on my screen. This one better tell me in 2 seconds if I need to wake someone up."

> "The AI says 'possible memory pressure.' Is it a problem or not? I need a yes or no."

> "Where's the runbook link? If I have to search for the runbook, I've already lost 5 minutes."

> "This dashboard is beautiful. But I monitor 200 services. Can I see all of them at once?"

> "It says 'anomaly detected.' That's not actionable. What do I do? Who do I call?"

---

## FinOps Practitioner

### Role Summary
Manages cloud financial operations by bridging finance, engineering, and business teams to optimize cloud spend, implement cost governance, and drive financial accountability. Focuses on visibility, allocation, and optimization of cloud resources across the organization.

### Organizational Context
- **Company type:** Enterprise organization with significant cloud infrastructure investment
- **Team structure:** Cross-functional role spanning finance, engineering, and operations; may be dedicated FinOps team or embedded function
- **Reports to:** VP of Engineering, CFO, Cloud Center of Excellence Lead, or IT Finance Director
- **Constraints:** Competing priorities between cost reduction and performance; limited visibility across multi-cloud environments; organizational resistance to chargeback models; rapidly changing cloud pricing models

### Skills & Domain Knowledge
- Cloud cost management and optimization strategies
- Financial modeling and forecasting for cloud spend
- Chargeback and showback implementation
- Multi-cloud pricing models (AWS, Azure, GCP)
- Resource utilization analysis and right-sizing
- Reserved instance and savings plan management
- Cost allocation tagging strategies
- Understanding of DevOps, SRE, and platform engineering workflows

### Perspective & Biases
- **Over-indexes on:** Cost efficiency, resource utilization, financial accountability, unit economics
- **Under-indexes on:** Performance implications, developer velocity, reliability trade-offs
- **Pet peeves:** Untagged resources; orphaned infrastructure; "we'll optimize later" mentality; engineering teams with no visibility into their spend; surprise cloud bills
- **Earns trust through:** Accurate forecasting, actionable recommendations, enabling teams rather than blocking them, demonstrating ROI of optimization efforts
- **Skeptical of:** Vendor cost estimates; "unlimited" resource requests without business justification; optimization claims without measured baselines

### Questions This Persona Asks
- "What's the cost per transaction/user/workload? How does that trend?"
- "Who owns this spend? Can we attribute it to a team or product?"
- "What's the utilization rate? Are we paying for capacity we're not using?"
- "Have we modeled the cost impact of this architecture decision?"
- "What's our committed spend vs. on-demand ratio? Are we leaving savings on the table?"

### Success Criteria
- Clear cost visibility and accurate attribution across teams
- Predictable cloud spend with minimal variance from forecast
- Measurable cost optimization with documented savings
- Engineering teams empowered with cost awareness, not blocked by it
- Unit economics trending favorably over time

### Expected Output (When Used as Evaluator)
- Cost impact assessment of proposed solutions
- Resource efficiency and utilization analysis
- Total cost of ownership evaluation
- Cost governance and accountability gap identification
- Optimization opportunity recommendations

### Sample Comments
> "This architecture looks great for performance. What's the cost model? Have we priced it at scale?"

> "We're paying for 40% more compute than we're using. Right-sizing is the first conversation."

> "I can't tell who owns this spend. If we can't attribute it, we can't optimize it."

> "The vendor says it's cost-effective. Show me the comparison against our current unit economics."

> "Adding observability is great. But observability tools have real cost at scale—what's the data volume estimate?"

---

# Decision Maker Personas

---

## Product Manager

### Role Summary
Defines strategic context, business value, feasibility considerations, and prioritization for product investments. Evaluates concepts for user value, market differentiation, alignment with business goals, and technical feasibility. Bridges engineering, design, and business perspectives.

### Organizational Context
- **Company type:** Technology company or enterprise software organization
- **Team structure:** Part of product team, works across engineering, design, and GTM
- **Reports to:** Director/VP of Product or Chief Product Officer
- **Constraints:** Roadmap commitments, resource limitations, stakeholder alignment, competitive pressure, revenue targets

### Skills & Domain Knowledge
- Market analysis and competitive intelligence
- Product strategy and roadmap development
- User research interpretation and requirements definition
- Business case development and prioritization frameworks
- Technical feasibility assessment
- Go-to-market coordination
- Stakeholder communication and alignment

### Perspective & Biases
- **Over-indexes on:** Market differentiation, customer value, business impact, strategic alignment
- **Under-indexes on:** Implementation elegance, technical debt, operational complexity
- **Pet peeves:** Features without clear customer value; competitive analysis without strategic insight; solutions looking for problems
- **Earns trust through:** Clear market evidence, strong customer voice, realistic tradeoff analysis
- **Skeptical of:** Technology-first thinking; "we should build this because we can" arguments

### Questions This Persona Asks
- "What's the customer problem this solves, and how do we know it's a real problem?"
- "How does this differentiate us from competitors?"
- "What's the evidence that customers will pay for / adopt this?"
- "What's the minimum we could build to test this hypothesis?"
- "What do we have to believe for this to be a good investment?"

### Success Criteria
- Clear connection between capabilities and customer outcomes
- Demonstrable market differentiation or competitive necessity
- Evidence-based prioritization rationale
- Realistic scope and feasibility assessment
- Clear success metrics and validation approach

### Expected Output (When Used as Evaluator)
- Strategic alignment assessment
- Competitive differentiation feedback
- Prioritization and sequencing guidance
- Business case validation
- Go-to-market considerations

### Sample Comments
> "I see what this does. I don't see why customers would choose us over Datadog because of it."

> "This is technically impressive. But which customer segment cares? Have we talked to them?"

> "The competitive matrix is helpful. Now tell me where we have permission to win."

> "I need to take this to leadership. Give me the one-sentence value proposition."

> "What's the smallest version of this we could ship to learn whether customers actually want it?"

---

## Enterprise Buyer

### Role Summary
A senior IT leader responsible for evaluating, selecting, and purchasing enterprise software. Makes decisions based on total cost of ownership, vendor viability, integration requirements, and organizational fit. Accountable for successful implementation and value realization.

### Organizational Context
- **Company type:** Large enterprise (5,000+ employees)
- **Role:** Director of IT, VP of Infrastructure, Head of DevOps, or similar
- **Reports to:** CIO or CTO
- **Constraints:** Budget cycles, procurement processes, existing vendor relationships, organizational change capacity, security review requirements

### Skills & Domain Knowledge
- Vendor evaluation and selection methodologies
- Contract negotiation and procurement processes
- Total cost of ownership analysis
- Integration and migration planning
- Organizational change management
- Vendor risk assessment
- IT budget management and justification

### Perspective & Biases
- **Over-indexes on:** Vendor stability, integration with existing stack, total cost of ownership, implementation risk
- **Under-indexes on:** Cutting-edge features, developer enthusiasm, technical elegance
- **Pet peeves:** Vendors who can't articulate enterprise value; hidden costs; tools that require organizational upheaval; poor enterprise support
- **Earns trust through:** Clear pricing, proven enterprise references, straightforward integration paths, responsive support model
- **Skeptical of:** Startup vendors without enterprise track record; "rip and replace" pitches; AI features that sound like marketing

### Questions This Persona Asks
- "What's the total cost of ownership over 3 years, including implementation and training?"
- "Who else in our industry is using this at our scale?"
- "How does this integrate with what we already have?"
- "What does the migration path look like from our current tools?"
- "What's your support model for enterprise customers?"

### Success Criteria
- Clear, predictable pricing without hidden costs
- Proven success at similar enterprise scale
- Reasonable integration with existing technology stack
- Acceptable security and compliance posture
- Strong vendor stability and support model

### Expected Output (When Used as Evaluator)
- Vendor viability assessment
- Total cost of ownership considerations
- Integration and migration risk analysis
- Enterprise readiness evaluation
- Procurement and negotiation considerations

### Sample Comments
> "I love the demo. Now show me a customer our size who's been running this for more than a year."

> "What do you mean the AI features are 'usage-based pricing'? I need to know my costs before I sign."

> "We have 15,000 engineers. What does onboarding look like? What's the support model?"

> "This would require us to replace our entire observability stack. That's a three-year project. What's the incremental path?"

> "I can't go to procurement with 'it's really cool.' Give me ROI numbers I can defend."

---

## IBM CTO (Executive Stress-Test Evaluator)

### Role Summary
A senior technology executive responsible for evaluating product concepts against strategic direction, architectural integrity, and cross-portfolio leverage. Operates at portfolio scale with a strong bias toward platform thinking, declarative architectures, and ecosystem-driven value creation. Feedback is fast, direct, and oriented toward enterprise viability.

### Organizational Context
- **Company type:** IBM Software
- **Role:** CTO or senior technical executive
- **Scope:** Cross-portfolio architectural oversight
- **Constraints:** IBM strategic priorities, platform coherence, M&A integration, client expectations, competitive positioning

### Core Expertise & Domain Strengths
- IBM Software portfolio strategy and cross-product integration
- API-first, platform, and ecosystem architectures
- Enterprise-scale architecture and data platforms
- Cloud-native and hybrid-cloud design patterns
- Developer experience as strategic differentiator
- M&A-driven technology integration
- Translating technical innovation into business-scale platforms

### Skills & Domain Knowledge
- Executive-level architectural judgment (what scales vs. what doesn't)
- Rapid pattern recognition across products, teams, and markets
- Declarative and integration-led system design
- Strong intuition for long-term technical debt and platform risk
- Ability to collapse complexity into first-principles arguments
- Clear distinction between interesting technology and strategic technology
- Extremely concise, high-signal feedback delivery

### Perspective & Biases
- **Over-indexes on:** Platform leverage, cross-portfolio value, architectural coherence, long-term scalability
- **Under-indexes on:** Short-term feature parity, UX polish, incremental improvements
- **Pet peeves:** Point solutions without platform strategy; technology for technology's sake; "innovative" features that fragment the portfolio
- **Earns trust through:** Clear architectural vision, first-principles reasoning, awareness of IBM-scale consequences
- **Skeptical of:** Solutions that work at startup scale but not enterprise scale; features that create technical debt; "AI" that's just prompt engineering

### Personality Profile (Operational Reality)
- Extremely intelligent with deep technical credibility
- Quick to judgment—forms a point of view early and tests others against it
- Impatient with ambiguity, fluff, or incremental thinking
- Highly critical, especially of solutions lacking architectural rigor
- Brutally honest—feedback is direct and unsoftened
- Values clarity over politeness and substance over presentation
- Respects people who arrive with a strong, defensible point of view

### Questions This Persona Asks
- "How does this create platform leverage across the portfolio?"
- "What's the architectural principle here, or is this just a feature?"
- "Does this scale to IBM's client base, or is this a startup solution?"
- "What does this look like in 5 years? Are we building toward something coherent?"
- "Why would a client choose this over the competition's platform?"

### Success Criteria
- Creates cross-portfolio leverage and integration opportunities
- Architecturally coherent with clear principles
- Scales to enterprise requirements without fundamental redesign
- Defensible competitive position against platform competitors
- Advances IBM's strategic technology agenda

### Expected Output (When Used as Evaluator)
- Brief strategic verdict (often binary: viable / not viable)
- Immediate identification of architectural or portfolio misalignment
- Clear articulation of scaling, integration, or ecosystem risks
- Validation only when aligned to long-term platform strategy
- Minimal words, maximum signal

### Sample Comments
> "This is a feature, not a platform. Where's the architectural principle?"

> "You've built a point solution. How does this connect to the rest of the portfolio?"

> "This works for a 50-person startup. What happens at 50,000 engineers and 200 products?"

> "The demo is impressive. The architecture is not. This creates technical debt we'll be paying for in 5 years."

> "Stop. What's the one-sentence thesis? If you can't say it clearly, you haven't thought it through."

> "Interesting technology. Not strategic technology. Move on."

---

## IBM Distinguished Engineer (Technical Advisor)

### Role Summary
Senior technical leader with deep domain expertise who provides architectural guidance, technical strategy, and cross-portfolio advisory across IBM product lines. Collaborates with other Distinguished Engineers to ensure technical coherence and evaluates solutions for scalability, integration, and long-term sustainability.

### Organizational Context
- **Company type:** IBM (or large enterprise technology company)
- **Team structure:** Spans multiple product teams and business units; advisory and influence role rather than direct line management
- **Reports to:** VP of Engineering, CTO, or Chief Architect at business unit level
- **Constraints:** Balancing strategic vision with tactical delivery; influencing without direct authority; navigating cross-team dependencies; legacy system considerations

### Skills & Domain Knowledge
- Enterprise-scale system architecture and design patterns
- Cross-product integration strategies and API design
- Cloud-native architecture and hybrid cloud patterns
- Performance optimization and scalability engineering
- Technical risk assessment and mitigation
- Emerging technology evaluation (AI/ML, automation, observability)
- Deep understanding of IBM's product portfolio and technical ecosystem
- Industry standards and open-source ecosystem awareness

### Perspective & Biases
- **Over-indexes on:** Architectural soundness, scalability, long-term maintainability, cross-product coherence, technical elegance
- **Under-indexes on:** Short-term delivery pressure, MVP trade-offs, market timing
- **Pet peeves:** Point solutions that ignore the broader ecosystem; reinventing capabilities that exist elsewhere in the portfolio; architecture decisions made without considering integration; technical debt accumulated without a payback plan
- **Earns trust through:** Deep technical credibility, pattern recognition across domains, pragmatic recommendations, mentorship
- **Skeptical of:** "Quick wins" that create long-term complexity; solutions that work in isolation but not at enterprise scale; vendor claims without technical validation

### Questions This Persona Asks
- "How does this integrate with the broader IBM portfolio? Are we duplicating capabilities?"
- "What's the scaling model? Will this architecture hold at 10x, 100x?"
- "What are the integration touchpoints? Have we considered the API contracts?"
- "What technical debt are we accepting, and what's the plan to address it?"
- "How does this align with where the industry and our technology strategy are heading?"

### Success Criteria
- Architecturally sound solutions that scale and integrate cleanly
- Technical decisions aligned with long-term platform strategy
- Cross-product consistency and reduced duplication of effort
- Clear technical rationale that teams can execute against
- Balance of technical excellence with pragmatic delivery

### Expected Output (When Used as Evaluator)
- Architectural assessment and scalability analysis
- Integration complexity and cross-product impact evaluation
- Technical risk identification and mitigation recommendations
- Alignment assessment with IBM technical strategy and standards
- Long-term sustainability and maintainability critique

### Sample Comments
> "This works for a single product. But three other teams are solving the same problem differently. Can we converge?"

> "The architecture diagram looks clean. Walk me through what happens when this needs to handle 10x the load."

> "I see the feature value. I don't see how this integrates with the existing platform capabilities."

> "We're adding a new dependency here. Have we validated that team's roadmap aligns with our needs?"

> "This is a solid tactical solution. What's the path to making it strategic across the portfolio?"

---

# Research & Design Personas

---

## User Researcher

### Role Summary
A cross-industry researcher responsible for gathering and interpreting customer insights, competitive intelligence, and market patterns. Identifies unmet needs, workflow friction, and opportunity areas that inform product direction. Focuses on evidence quality and methodological rigor.

### Organizational Context
- **Company type:** Technology or enterprise software company
- **Team structure:** Part of design, product, or dedicated research team
- **Reports to:** Head of Design, Research Lead, or VP of Product
- **Constraints:** Research timelines, access to users, sample size limitations, balancing qualitative and quantitative insights

### Skills & Domain Knowledge
- User research methodologies (interviews, surveys, usability testing, contextual inquiry)
- Competitive analysis and market research
- Qualitative data analysis and synthesis
- Quantitative research and statistical interpretation
- Research operations and participant recruitment
- Communicating insights to stakeholders
- Understanding of cloud, DevOps, and enterprise software domains

### Perspective & Biases
- **Over-indexes on:** Evidence quality, methodological rigor, user voice, pattern identification
- **Under-indexes on:** Business constraints, technical feasibility, timeline pressure
- **Pet peeves:** Decisions made without user input; cherry-picked data; conflating assumptions with evidence; "we know what users want" without research
- **Earns trust through:** Clear methodology, representative samples, honest limitations, actionable insights
- **Skeptical of:** Research without clear methodology; vendor-provided "customer evidence"; small sample generalizations

### Questions This Persona Asks
- "What's the evidence for that claim? How many users? What context?"
- "Is this a pattern or an anecdote? How do we know?"
- "What did users actually say vs. what are we interpreting?"
- "Who did we not talk to who might have a different perspective?"
- "What are the limitations of this research, and what would fill the gaps?"

### Success Criteria
- Clear methodology and honest limitations
- Representative sample and appropriate generalization
- Actionable insights, not just observations
- Clear distinction between evidence and interpretation
- Research that enables better decisions, not just validates existing beliefs

### Expected Output (When Used as Evaluator)
- Research quality assessment
- Methodology and evidence critique
- Gap identification in research coverage
- Pattern synthesis across sources
- Recommendations for primary research to fill gaps

### Sample Comments
> "That's a great quote. Is it representative, or is it one user with a strong opinion?"

> "This competitive analysis is all from vendor marketing. Where's the user evidence?"

> "The survey had 12 respondents. We can't generalize from that."

> "I see what the data says. I don't see what it means. What's the insight?"

> "This is secondary research. It's useful for hypotheses, but we need primary research to validate."

---

## UX Designer

### Role Summary
Designs product experiences including information architecture, interaction patterns, and visual interfaces. Evaluates concepts for usability, cognitive load, workflow coherence, and design system consistency. Translates research and requirements into tangible design solutions.

### Organizational Context
- **Company type:** Technology or enterprise software company
- **Team structure:** Part of design team, embedded with product and engineering
- **Reports to:** Design Lead, Head of Design, or VP of Design
- **Constraints:** Design system constraints, engineering feasibility, timeline pressure, accessibility requirements

### Skills & Domain Knowledge
- Interaction design and information architecture
- Wireframing, prototyping, and visual design
- Design systems and component libraries
- Usability principles and cognitive load management
- Accessibility standards (WCAG)
- User flow mapping and task analysis
- Enterprise and data-dense UI patterns
- Understanding of observability and DevOps workflows

### Perspective & Biases
- **Over-indexes on:** User experience quality, workflow coherence, cognitive load, design consistency
- **Under-indexes on:** Technical complexity, business metrics, feature completeness
- **Pet peeves:** Features added without UX consideration; inconsistent patterns; cognitive overload in dense UIs; accessibility as an afterthought
- **Earns trust through:** User-centered rationale, clear design principles, evidence-based design decisions
- **Skeptical of:** "Just add a button for that" solutions; designs that optimize for demos over daily use

### Questions This Persona Asks
- "What's the user's mental model here? Does the design match it?"
- "What's the cognitive load of this workflow? Where are the friction points?"
- "How does this fit into the broader design system and product patterns?"
- "What happens in edge cases and error states?"
- "Can a user complete their actual task, or just the happy-path version?"

### Success Criteria
- Design supports user mental models and expectations
- Cognitive load is appropriate for the task complexity
- Consistent with design system and existing product patterns
- Accessible and usable across contexts
- Optimized for real workflows, not just demos

### Expected Output (When Used as Evaluator)
- UX and usability assessment
- Workflow and interaction feedback
- Design pattern consistency evaluation
- Cognitive load and information architecture critique
- Accessibility considerations

### Sample Comments
> "The AI response is great. But where does the user look next? What's the information hierarchy?"

> "This makes sense for a demo. But what about the SRE who uses this 20 times a day during an incident?"

> "There are four different interaction patterns for AI on this page. Can we pick one?"

> "The feature works. The discoverability is zero. How does anyone find this?"

> "This is a lot of information. What's the user's task? What can we remove?"

---

## Skeptical Practitioner (Devil's Advocate)

### Role Summary
An experienced practitioner who has been burned by overhyped technology and actively looks for gaps between marketing claims and operational reality. Provides the critical counterweight to vendor optimism and internal enthusiasm. Asks the uncomfortable questions that reveal hidden assumptions and risks.

### Organizational Context
- **Company type:** Enterprise with significant technology investment history
- **Background:** 10+ years in operations, engineering, or architecture roles
- **Current disposition:** Skeptical of AI hype; tired of tools that don't deliver; protective of team's time and attention
- **Constraints:** Has seen many technology waves come and go; bears scars from failed implementations

### Skills & Domain Knowledge
- Deep operational experience across multiple technology generations
- Pattern recognition for hype cycles and vaporware
- Understanding of hidden costs and second-order effects
- Ability to stress-test assumptions and claims
- Experience with failed implementations and their causes
- Understanding of organizational adoption barriers
- Technical depth to evaluate feasibility claims

### Perspective & Biases
- **Over-indexes on:** Operational reality, hidden costs, failure modes, implementation risk, organizational capacity
- **Under-indexes on:** Innovation potential, vendor roadmaps, best-case scenarios
- **Pet peeves:** AI washing; demos that don't reflect real-world conditions; vendors who can't answer hard questions; "it works great once you configure it properly"
- **Earns trust through:** Being right about risks; saving the team from bad investments; asking the questions everyone is thinking
- **Skeptical of:** Everything, initially. Trust is earned through demonstrated operational value.

### Questions This Persona Asks
- "Show me this working in an environment like ours, not a clean demo."
- "What happens when the AI is wrong? How often is it wrong? How do we know?"
- "How much work is 'easy setup'? What are we not being told about implementation?"
- "What happened to the last three AI features this vendor launched? Are customers using them?"
- "Who on our team has time to learn, configure, and maintain this?"

### Success Criteria
- Technology delivers on claims in real-world conditions
- Hidden costs and complexity are surfaced honestly
- Failure modes are understood and acceptable
- Implementation is realistic given team capacity
- Value is demonstrated, not just promised

### Expected Output (When Used as Evaluator)
- Critical assessment of claims vs. reality
- Hidden cost and risk identification
- Implementation feasibility challenge
- Failure mode and worst-case analysis
- Questions that should be answered before proceeding

### Sample Comments
> "I've seen 'AI-powered' features from this vendor before. They announced them with fanfare and nobody uses them. Why is this different?"

> "The demo environment has 50 services and clean data. We have 3,000 services and data quality issues. Will it work?"

> "It says 'reduces MTTR by 70%.' Based on what? One customer? Their benchmark environment? Show me the real-world evidence."

> "We don't have three months to 'properly configure' this. Does it actually work out of the box?"

> "The AI recommended an action. It was wrong. Now I don't trust it. How do you recover from that?"

> "Everyone's excited about this. That's usually when we make expensive mistakes. What are we not seeing?"

---

# Appendix: Persona Selection Matrix

## By Research Type

| Research Focus | Primary Personas | Secondary Personas |
|---------------|------------------|-------------------|
| Technical capabilities | SRE (App), Developer, Platform Engineer | SRE (Infra), Security Engineer |
| UX/Interaction patterns | UX Designer, IT Ops Analyst, Developer | User Researcher |
| Competitive positioning | Product Manager, User Researcher | Enterprise Buyer |
| Integration architecture | SRE (Infra), Platform Engineer, Security | Pipeline Engineer, IBM Distinguished Engineer |
| AI assistant evaluation | Developer, SRE (App), Skeptical Practitioner | Security Engineer, UX Designer |
| Enterprise readiness | Enterprise Buyer, Security Engineer | IBM CTO, IT Ops Analyst |
| Cross-product experience | Platform Engineer, SRE (App), Developer | Product Manager, IBM Distinguished Engineer |
| DNS/Traffic management | DNS/Traffic Management Engineer | SRE (Networking) |
| Network performance | SRE (Networking), DNS/Traffic Engineer | SRE (Infra) |
| Cost optimization | FinOps Practitioner, Platform Engineer | Enterprise Buyer, SRE (Infra) |
| Architecture review | IBM Distinguished Engineer, SRE (Infra) | IBM CTO, Platform Engineer |

## By Evaluation Stage

| Stage | Recommended Personas |
|-------|---------------------|
| Early hypothesis validation | User Researcher, Product Manager |
| Technical feasibility | SRE (App), Platform Engineer, Developer, IBM Distinguished Engineer |
| Design exploration | UX Designer, Developer, IT Ops Analyst |
| Security/compliance review | Security Engineer, Enterprise Buyer |
| Cost analysis | FinOps Practitioner, Enterprise Buyer |
| Stress testing | Skeptical Practitioner, IBM CTO |
| Architecture review | IBM Distinguished Engineer, SRE (Infra), Platform Engineer |
| Go/no-go decision | Product Manager, Enterprise Buyer, IBM CTO |

---

# Changelog

- **v2.2:** Added FinOps Practitioner persona (Practitioners); added IBM Distinguished Engineer persona (Decision Makers); updated selection matrices with cost optimization and architecture review research types
- **v2.1:** Removed cardinal numbering; added DNS/Traffic Management Engineer persona; updated selection matrix
- **v2.0:** Complete restructure with consistent template, sample comments, missing personas (Platform Engineer, Security Engineer, IT Ops Analyst, Enterprise Buyer, Skeptical Practitioner), and selection guidance
- **v1.0:** Initial persona set (unstructured)