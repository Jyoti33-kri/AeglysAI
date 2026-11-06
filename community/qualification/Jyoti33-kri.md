# AeglysAI Qualification Evidence

## 1. Environment
- GitHub Username: Jyoti33-kri
- Operating System: Windows
- .NET SDK: 8.x
- Git Version: 2.56.0
- Repository: AeglysAI
- Branch: qualification/Jyoti33-kri

## 2. Clone and Setup
- Forked the official AeglysAI repository.
- Cloned the fork locally.
- Opened the project using VS Code.
- Installed and used the .NET 8 SDK.
- Installed and configured Docker Desktop with WSL 2 support.
- Successfully completed the Docker-based local development workflow.

## 3. Docker Quick Start Validation
Successfully executed the following commands from the repository root:

- `./dev up` – Built and started the API with temporary local credentials.
- `./dev health` – Checked API health.
- `./dev demo` – Executed the A/B/C authorization demonstration.
- `./dev logs` – Inspected JSON decision audit logs.
- `./dev test` – Executed the Docker development test workflow.
- `./dev experiment my-smoke` – Executed the experiment workflow.
- `./dev down` – Stopped the development environment and removed its network.

## 4. Build and Run Evidence
Successfully started the API using:

`dotnet run --project src/AeglysAI.Api -- --urls http://localhost:5080`

- API listening address: http://localhost:5080
- Hosting environment: Production.

## 5. Test Results
- Experiments tests: 4 passed, 0 failed.
- Integration tests: 93 passed, 0 failed.
- Total: 97 passed, 0 failed, 0 skipped.

## 6. Architecture Understanding
AeglysAI is a risk-aware authorization platform.

It uses three authorization models:
- Model A: Role-Based Access Control (RBAC).
- Model B: RBAC combined with Attribute-Based Access Control (ABAC).
- Model C: RBAC, ABAC and contextual risk evaluation.

A request is authenticated using a signed JWT and evaluated against applicable authorization policies and context. The system produces an authorization decision and records audit information.

STEP_UP and LIMIT are recommendations; automatic challenge and rate-limit enforcement are not yet implemented.

## 7. Technical Observation
The API successfully started locally using .NET 8. The test execution reported 97 passing tests and zero failures.

An important limitation is that STEP_UP and LIMIT decisions are recommendations rather than automatically enforced actions.

## 8. Suggested Improvement
Implement enforcement for STEP_UP and LIMIT decisions.

STEP_UP could require additional user verification, while LIMIT could apply configurable request rate limits.

This would improve the practical security of the authorization platform.

## 9. Validation Approach
- Execute the existing unit and integration tests.
- Validate the Docker-based development workflow.
- Add tests for STEP_UP and LIMIT enforcement.
- Verify that restricted requests are handled correctly.
- Check that decisions are recorded in audit logs.

## 10. Evidence
- Build log: community/qualification/build-log.txt
- Docker Quick Start: Completed
- API startup: Successful
- Test execution: 97 passed, 0 failed, 0 skipped