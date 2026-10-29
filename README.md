# PulsarGuard

**Observe. Detect. Secure.**

PulsarGuard is a planned cloud-native security monitoring platform that combines network intrusion detection, DevSecOps automation, cloud deployment, and observability in one project.

The project uses Suricata to detect suspicious network activity and aims to provide a web dashboard for analyzing alerts, reviewing security events, and monitoring application health.

> **Project status:** Initial development. Features will be implemented and verified incrementally.

## Objectives

- Detect selected suspicious HTTP requests using Suricata IDS rules.
- Capture and analyze authorized network traffic using TCPDump and PCAP files.
- Process Suricata EVE JSON events through a Python backend.
- Provide a web dashboard for security alert investigation.
- Automate testing, code quality checks, and security scans through CI/CD.
- Deploy the application to AWS using secure configuration and least-privilege access.
- Monitor application health and metrics using Prometheus and Grafana.

## Planned Technology Stack

| Area                   | Technology                      |
| ---------------------- | ------------------------------- |
| Intrusion detection    | Suricata                        |
| Traffic capture        | TCPDump, PCAP                   |
| Backend API            | Python, FastAPI                 |
| Frontend               | Next.js, JavaScript             |
| Initial storage        | SQLite                          |
| Testing                | pytest, HTTPX                   |
| Python code quality    | Ruff                            |
| Containers             | Docker, Docker Compose          |
| CI/CD                  | GitLab CI/CD and GitHub Actions |
| Cloud                  | AWS                             |
| Metrics and dashboards | Prometheus, Grafana             |
| Version control        | Git                             |

Technologies will be introduced incrementally as the project develops.

## Planned Features

### 1. Network Intrusion Detection

- Detect requests to a designated HTTP URI.
- Detect a specified suspicious User-Agent.
- Validate Suricata signatures before replaying captures.
- Analyze PCAP files and EVE JSON alert records.
- Compare broad and refined signatures to understand false positives.

### 2. Security Event API

- Parse Suricata EVE JSON events.
- Validate incoming event data.
- Store selected alert records in SQLite.
- Provide API endpoints for alert retrieval, filtering, and summary statistics.
- Expose an application health endpoint.

### 3. Security Dashboard

- Display security alert summaries.
- List alerts and relevant event details.
- Filter alerts by supported fields.
- Present useful visualizations and application status.
- Support responsive layouts and light/dark themes.

### 4. DevSecOps and CI/CD

- Use meaningful Conventional Commits.
- Run automated backend tests and frontend build checks.
- Apply Python linting and practical dependency security checks.
- Build and validate container images.
- Maintain separate development, pre-deployment, and production workflows as appropriate.

### 5. Cloud and Observability

- Prepare a controlled AWS deployment.
- Apply least-privilege IAM permissions and secure configuration.
- Collect application metrics using Prometheus.
- Build monitoring dashboards in Grafana.
- Validate health checks, logs, and deployment readiness.

## Architecture Overview

The planned event flow is:

1. Authorized test traffic reaches a controlled HTTP service.
2. Suricata inspects traffic and generates alert events.
3. EVE JSON events are processed by the FastAPI backend.
4. Selected alerts are stored in SQLite.
5. The Next.js frontend retrieves and displays alert information.
6. CI/CD validates changes, while Prometheus and Grafana support application observability.

This architecture describes the intended design; components will be integrated and tested in later development tasks.

## Security and Authorized Testing

PulsarGuard is intended for defensive security education and authorized monitoring.

- Test only systems and traffic for which explicit authorization has been granted.
- Keep the original lab's Guard/Runner experiment limited to the assigned partner and TCP port 8080.
- Do not scan unrelated systems, campus networks, gateways, or public hosts.
- Do not disable institutional firewalls or modify routing settings for the lab.
- Treat IDS alerts as detection evidence, not proof that traffic was blocked.
- Do not commit credentials, private keys, access tokens, or other secrets.
- Do not expose the controlled lab HTTP service publicly.

The initial IDS experiments are passive detection exercises. Prevention and automated blocking are outside the initial scope.

## Development Workflow

The planned workflow uses the following Git branches:

- `development` — ongoing implementation and testing.
- `pre-deployment` — integration and deployment-readiness validation.
- `main` — stable, verified releases.

Changes will be kept small, reviewed before staging, and committed using Conventional Commit messages such as `feat`, `fix`, `test`, `security`, `chore`, `ci`, `docs`, and `refactor`.

Automated checks and deployment protections will be introduced as their corresponding workflows are implemented.

## Project Roadmap

| Phase      | Focus                                                  |
| ---------- | ------------------------------------------------------ |
| Days 1–2   | Scope, Git workflow, documentation, backend foundation |
| Days 3–4   | Suricata rules, traffic capture, PCAP replay           |
| Days 5–6   | FastAPI, event processing, SQLite                      |
| Days 7–8   | Next.js dashboard                                      |
| Days 9–10  | Docker, testing, security checks, CI/CD                |
| Days 11–12 | AWS deployment                                         |
| Days 13–14 | Prometheus, Grafana, final verification                |

## Getting Started

Development setup instructions will be added after the required environments and application components have been established.

## Learning Goals

PulsarGuard is designed to build practical skills in:

- Network intrusion detection and security event analysis.
- Python API development and frontend integration.
- Automated testing and secure software delivery.
- Containerization and AWS fundamentals.
- Metrics, monitoring, and operational troubleshooting.

## Disclaimer

PulsarGuard is an educational project under development. It is not a substitute for a professionally managed security operations platform or a comprehensive enterprise intrusion prevention system.
