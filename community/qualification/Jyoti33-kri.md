\# AeglysAI Qualification Evidence



\## 1. Environment

\- GitHub Username: Jyoti33-kri

\- Operating System: Windows

\- .NET SDK: 8.x

\- Git Version: 2.56.0

\- Repository: AeglysAI

\- Branch: qualification/Jyoti33-kri



\## 2. Clone and Setup

\- Forked the official AeglysAI repository.

\- Cloned the fork locally.

\- Opened the project using VS Code.

\- Installed and used the .NET 8 SDK.

\- Docker Quick Start setup: Pending.



\## 3. Build and Run Evidence

\- Executed `dotnet restore`.

\- Executed `dotnet build`.

\- Successfully started the API using:

&#x20; `dotnet run --project src/AeglysAI.Api -- --urls http://localhost:5080`

\- API listening address: http://localhost:5080

\- Hosting environment: Production.



\## 4. Test Results

\- Experiments tests: 4 passed, 0 failed.

\- Integration tests: 93 passed, 0 failed.

\- Total: 97 passed, 0 failed, 0 skipped.



\## 5. Architecture Understanding

AeglysAI is a risk-aware authorization platform.



It uses three authorization models:

\- Model A: Role-Based Access Control (RBAC).

\- Model B: RBAC combined with Attribute-Based Access Control (ABAC).

\- Model C: RBAC, ABAC and contextual risk evaluation.



A request is authenticated using a signed JWT and evaluated against the applicable authorization policies and context. The system produces an authorization decision and records audit information.



STEP\_UP and LIMIT are recommendations; automatic challenge and rate-limit enforcement are not yet implemented.



\## 6. Technical Observation

The API successfully started locally using .NET 8. The test execution reported 97 passing tests and zero failures.



An important limitation is that STEP\_UP and LIMIT decisions are recommendations rather than automatically enforced actions.



\## 7. Suggested Improvement

Implement enforcement for STEP\_UP and LIMIT decisions.



STEP\_UP could require additional user verification, while LIMIT could apply configurable request rate limits.



This would improve the practical security of the authorization platform.



\## 8. Validation Approach

\- Run the existing unit and integration tests.

\- Add tests for STEP\_UP and LIMIT enforcement.

\- Verify that restricted requests are handled correctly.

\- Check that decisions are recorded in audit logs.



\## 9. Evidence

Build log: community/qualification/build-log.txt



Docker-based Quick Start and demo validation remain pending.

