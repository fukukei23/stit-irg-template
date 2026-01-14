# PROJECT_PROFILE_TEMPLATE.md

> [!IMPORTANT]
> **THIS IS A TEMPLATE.**
> Do not treat this file as a default profile.
> Downstream projects MUST copy this file to `PROJECT_PROFILE_<PROJECT_KEY>.md` and fill in the details.
> Replace all placeholders (e.g., `<PROJECT_KEY>`) with actual project information.

Version: 0.1.0  
LastUpdated: YYYY-MM-DD  

ArchitectureRef:

- File: <Path to your ARCHITECTURE_<PROJECT_ID>.md>
- Version: <Target Version>
- Commit: <Target Commit Hash or N/A>

---

## 1. Project Name

- System Name: <Official System Name>
- Domain: <Business Domain / Area of Operation>
- Operation Name: <Internal Project Codename or Short Name>

---

## 2. Purpose / Scope

### 2.1 Purpose

- <Describe the primary goals and objectives of this project.>
- <What problem are we trying to solve?>

### 2.2 In Scope

- <List features and domains included in this project.>
- <Example: Specific modules, target platforms, or user types.>

### 2.3 Out of Scope

- <Explicitly list what is NOT handled by this project.>
- <Helps prevent requirement creep.>

---

## 3. Operation Mode

- <Define how the system is deployed and used (e.g., Local CLI, Single-user Web, SaaS).>
- <Specify any fail-fast or safety-first handling preferences.>

---

## 4. Data Store Policy

- <Define the primary database or storage technology (e.g., SQLite, PostgreSQL, CSV).>
- <Document constraints for future scaling (e.g., "Must use ORM", "No hardcoded paths").>

---

## 5. Pricing / FX Policy

- <If applicable, define how costs, currency exchange, or financial calculations are handled.>
- <Document external API dependencies or accuracy requirements.>

---

## 6. Data Acquisition Policy

- <Define how data is gathered (e.g., Manual Import, LLM Generation, API calls).>
- <Document risks and constraints related to scraping or external data sources.>

---

## 7. Code Quality Policy

- <Linter and formatter requirements (e.g., ruff, black, flake8).>
- <Testing coverage goals or static analysis requirements.>

---

## 8. Automation Boundary

- <Define the line between AI/Automated actions and Human intervention.>
- <What steps require manual approval?>

---

## 9. Failure Handling Policy

- <Standard behavior during errors (e.g., "Immediate halt", "Log and continue").>
- <Retry logic and alerting requirements.>

---

## 10. Security Baseline

- <Mandatory security practices (e.g., "ENV for secrets", "No PII in LLM prompts").>
- <Input validation and sanitization standards.>

---

## 11. Decision Summary

- <High-level architectural/governance stance (e.g., "Safety over speed", "Minimal dependencies").>
- <The guiding philosophy for Phase 1 code.>
