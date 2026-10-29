# PulsarGuard Development Standards

## 1. General Principles

- Keep changes small, focused, and reviewable.
- Prefer readable code and simple solutions.
- Never commit credentials, access tokens, or private keys.
- Document security-sensitive decisions.

## 2. Git Workflow

- Develop on the development branch.
- Review git status and git diff before staging changes.
- Stage only files relevant to the current task.
- Use Conventional Commit messages.
- Verify the working tree and push result after committing.
- Promote changes to pre-deployment and main only after appropriate validation.

## 3. Backend Quality

- Use Python and FastAPI for backend development.
- Write automated tests with pytest and HTTPX.
- Use Ruff for Python linting and formatting checks.
- Validate external input and return appropriate HTTP errors.
- Keep secrets and environment-specific settings outside source code.

## 4. Frontend Quality

- Use Next.js with JavaScript.
- Keep components focused and reusable.
- Validate user input and handle API errors clearly.
- Verify production builds before promoting changes.

## 5. Security Requirements

- Use only authorized systems and test traffic.
- Preserve the assigned Guard/Runner and TCP port 8080 restrictions for the original IDS practical.
- Never disable institutional firewalls or change routing for the lab.
- Treat IDS alerts as detection evidence, not proof of prevention.
- Review dependencies and container images for known vulnerabilities.
- Use least-privilege access and secure configuration.

## 6. CI/CD and Deployment

- Automate tests, linting, and build checks.
- Introduce dependency and container security checks.
- Use health checks for deployed services.
- Never expose secrets in logs or pipeline output.
- Validate deployment changes before promoting releases.

## 7. Observability

- Use Prometheus for application metrics.
- Use Grafana for monitoring dashboards.
- Record useful errors without exposing sensitive information.
- Verify application health after deployment.

## 8. Definition of Done

A task is complete when:

- The intended change is implemented.
- Relevant checks pass.
- The diff has been reviewed.
- No unintended files or secrets are staged.
- A meaningful Conventional Commit is created.
- The push is verified when a remote is configured.
- Documentation is updated when necessary.

These standards describe the intended workflow. Automated enforcement will be introduced as the relevant tools are implemented.
