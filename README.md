# Hi, I'm Gabriel Sant'Ana

AWS Solutions Architect and Data Engineer based in Brazil. I spend most of my time designing cloud architectures and building data platforms that actually get used — not just documented.

My background is a bit unusual: I started in SAP ABAP development, which gave me a deep understanding of enterprise systems before I ever touched a cloud console. That transition from monolithic ERP logic to serverless AWS shaped how I think about modernization — I've been on both sides of the wall.

---

## What I actually work on

Most of my projects fall into one of three buckets: helping companies migrate or modernize their data infrastructure on AWS, building the connective tissue between SAP/Salesforce and cloud-native services, and prototyping things in AI/ML and DevOps that turn into real products.

I like the full arc — from scoping an architecture to writing the Glue jobs to making sure it holds under production load.

---

## Recent Projects

### S/4 AI Assistant
AI-powered chat assistant for querying SAP S/4HANA data in natural language. Users ask business questions — the system autonomously discovers the right OData API, analyzes its schema, executes the query, and returns formatted results. No hardcoded API knowledge, no SAP modifications.

`Amazon Bedrock AgentCore` `Strands Agents SDK` `Claude Haiku` `WebSocket API Gateway` `SQS FIFO` `Cognito (PKCE)` `CloudFront` `DynamoDB` `Terraform` `Python` `pytest`

Key details:
- 124 OData services in the agent's system prompt — the LLM selects the best API from context
- Auto-discovery of new APIs from `/$metadata` with smart caching
- Progressive rendering via chunked WebSocket delivery with markdown tables
- Full security: JWT auth, DOMPurify XSS prevention, SSRF protection, encryption at rest
- 40 unit tests covering tools, parser, client, and security

### S4Pilot — SAP Fiori Test Automation
End-to-end test automation for SAP Fiori S/4HANA using generative AI (Amazon Bedrock) to interpret test steps written in natural language and execute them in a real browser via WebDriverIO + wdi5.

`TypeScript` `Amazon Bedrock (Claude Haiku)` `WebDriverIO` `wdi5` `Vitest` `S3` `DynamoDB` `Secrets Manager` `Terraform`

Key details:
- Reads Excel test scripts from S3, each row is a natural language step (e.g., "Fill the Sales Org field with 1710")
- AI converts steps into executable commands (`CLICK`, `FILL`, `SELECT`, `NAVIGATE`, `VERIFY`, `CAPTURE`)
- Multi-layer element resolution: wdi5 native → UI5 API → CSS validation → DOM heuristic → specialized fallbacks
- Disk-based conversion cache with per-script isolation and automatic invalidation
- Confidence retry with exponential backoff when AI returns low confidence

### Numen Analytics for SAP (NAS)
Data lake solution that extracts SAP data into AWS for analytics and AI/ML. Built as an AWS CDK Python project with serverless architecture end to end.

`AWS CDK (Python)` `Glue` `Step Functions` `S3` `Athena` `Glue Data Catalog` `QuickSight`

Key details:
- Single parameterized Glue job extracts data from SAP S/4HANA via OData V2
- Dynamic catalog discovery — resolves SAP API paths at runtime (no hardcoded URLs)
- Step Functions orchestrates full-load and delta-load pipelines
- QuickSight dashboards: O2C Revenue Analysis, P2P Procurement Analysis
- Covers Sales, Procurement, Inventory, and Master Data domains

### AppFlow Connector for SAP OData V4
Custom Amazon AppFlow connector that enables native integration with SAP OData V4 APIs — something AppFlow doesn't support out of the box.

`Python` `Lambda` `Amazon AppFlow` `Terraform` `SAP OData V4`

Key details:
- Lambda-based connector with configuration, metadata, record, and validation handlers
- Terraform-managed infrastructure
- Parses OData V4 `$metadata` XML for dynamic entity/field discovery

### AS2 Server (Pharma EDI)
Proof of concept for an AS2-compliant server for pharmaceutical EDI data exchange, deployed entirely on AWS with CloudFormation.

`CloudFormation (YAML)` `Lambda` `S3` `Certificates`

---

## Stack

```
Cloud       AWS (primary) — 8 certifications, daily hands-on since 2020
AI/ML       Bedrock (AgentCore, Strands SDK, Converse API) · Claude · Prompt Engineering
Languages   Python (Boto3, PySpark, Pandas, httpx, pytest) · TypeScript · SQL · ABAP
Data        Glue · Athena · Redshift · Step Functions · S3 Data Lakes · ETL/ELT
IaC         Terraform · AWS CDK (Python) · CloudFormation
Serverless  Lambda · API Gateway (REST + WebSocket) · SQS · DynamoDB · Cognito
Frontend    CloudFront · SAP Fiori · UI5
Testing     pytest · Vitest · WebDriverIO · wdi5
Enterprise  SAP S/4HANA · SAP CRM · SAP OData (V2 + V4) · Salesforce
```

---

## Certifications

| | |
|---|---|
| AWS Solutions Architect – Professional | AWS Machine Learning – Specialty |
| AWS Data Analytics – Specialty | AWS Developer – Associate |
| AWS Solutions Architect – Associate | AWS Cloud Practitioner |
| SAP certifications | Salesforce certifications |

I took them seriously, not as resume checkboxes.

---

## Let's talk

[linkedin.com/in/gabrielsantana](https://www.linkedin.com/in/gabrielsantana/)
