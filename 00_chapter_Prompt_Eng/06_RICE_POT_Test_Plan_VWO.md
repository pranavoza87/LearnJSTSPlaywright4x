# VWO Test Plan

## 1. Test Plan ID and Title

**Test Plan ID:** TP-VWO-001 (locally assigned)  
**Title:** VWO Digital Experience Optimization Platform Test Plan  
**Version:** 1.0  
**Status:** Draft for review  
**Source PRD:** *VWO – Digital Experience Optimization Platform*, dated January 7, 2026  
**Prepared:** October 13, 2026

This document is a test plan derived from the supplied PRD. It defines planned coverage only; it does not report test execution or verified product behavior.

## 2. Objective and References

### Objective

Define a risk-based approach to assess the VWO capabilities described in the PRD, including experiment creation and analysis, behavioral insights, personalization, integrations, collaboration workflows, and stated non-functional requirements. The plan supports review of requirement coverage, test readiness, and unresolved prerequisites.

### References

- Supplied VWO product requirements document (PRD), dated January 7, 2026.
- No detailed acceptance criteria, product specifications, API contracts, screenshots, or implementation references were supplied.

### Product and users

VWO is described as a digital experience optimization and conversion rate optimization platform. The PRD identifies CRO specialists, product managers, UX designers, digital marketers, analysts, engineering teams, and business executives as users or stakeholders.

## 3. In Scope and Out of Scope

### In scope

- Functional evaluation planning for PRD requirements FR1–FR9.
- The A/B test setup and behavioral analysis flows described in the PRD.
- Relevant integration, regression, cross-browser/device, and non-functional testing, subject to approved scope and available environment support.
- Traceability from requirements and risks to planned coverage.
- Test readiness, access, data, environment, and stakeholder prerequisites.

### Out of scope

- Implementation or modification of VWO product code.
- Execution against a live or production tenant without explicit authorization and approved test access.
- Unspecified product behavior, undocumented interfaces, and exact error-message verification until requirements are supplied.
- Pricing and licensing validation; PRD pricing notes cite an external source and are not stated as product requirements.
- Future enhancements (AI suggestions, mobile SDK enhancements, predictive analytics, and ROI forecasting) unless separately approved as current scope.
- Penetration testing, formal compliance certification, or high-volume load testing unless separately scoped, authorized, and provisioned.

## 4. Requirements and Planned Coverage

The FR identifiers below are supplied in the PRD. Non-functional IDs NFR-01 through NFR-05 are assigned locally because the PRD does not number those requirements.

| Requirement | PRD priority / target | Planned coverage | Key dependency or clarification |
| --- | --- | --- | --- |
| FR1 — A/B, Split, and Multivariate Testing | Must | Plan functional tests for experiment creation with multiple variations; configuration, audience association, launch/monitoring, and completion where supported. Include invalid or incomplete configurations and boundary cases after acceptance criteria are defined. | Supported experiment types, lifecycle states, variation limits, and validation rules are not specified. |
| FR2 — SmartStats Engine | Must | Plan result-analysis checks for Bayesian output, result updates, interpretation, and consistency against approved statistical examples or oracle data. | Statistical calculations, confidence/decision rules, sample-size behavior, and expected result examples are not provided. |
| FR3 — Visual and Code Editor | Must | Plan setup and editing checks for WYSIWYG and developer-level workflows, preview, save/publish behavior, and supported browser/device QA. | Editor capabilities, supported code languages, save semantics, and testable acceptance criteria are not provided. |
| FR4 — Heatmaps and Session Recordings | Must | Plan collection and review of click, scroll, and focus interactions; recording access; and correlation to the selected page/session where supported. | Consent, sampling, masking, retention, supported browsers, and expected data latency are not specified. |
| FR5 — Audience Targeting | High | Plan segmentation checks for behavior and attributes, including geography where applicable; assess selection boundaries and whether the configured audience is applied as intended. | Available attributes, segment operators, precedence, and source-of-truth data are not specified. |
| FR6 — Real-time Reporting and Dashboards | Must | Plan dashboard and report checks for current experiment analytics, filters, metric display, and consistency with approved source data. | “Real-time” latency, refresh behavior, metrics, and report calculation rules are not defined. |
| FR7 — Personalization Engine | High | Plan segment-targeted content checks, eligibility and non-eligibility paths, and update behavior described as real time. | Personalization precedence, fallback behavior, content publishing, and latency criteria are not specified. |
| FR8 — Integration Connectors | High | Plan integration setup, data exchange, error handling, and reconciliation for integrations selected and enabled in the approved tenant. PRD examples include Google Analytics, Mixpanel, Shopify, Salesforce, Segment, Snowflake, WordPress, and Drupal. | The supported/contracted integration subset, credentials, sandbox endpoints, data mappings, and expected synchronization behavior are not provided. |
| FR9 — Collaboration and Workflow Management | Medium | Plan checks for central planning, collaboration, experiment backlog, and Kanban-style workflow actions, including role-appropriate access where confirmed. | Workflow states, permissions, collaboration actions, and audit expectations are not defined. |
| NFR-01 — Editing workflow performance (local ID) | Response within 2 seconds | Plan performance measurement for identified editing workflows under an agreed load and environment; capture response-time distributions and failures. | PRD does not define percentile, workload, measurement boundaries, or test data. Proposed thresholds require product approval. |
| NFR-02 — Security controls (local ID) | 2FA, role-based access control, activity logs | Plan verification of configured 2FA flows, permission boundaries, and activity-log coverage using approved accounts and a confirmed role matrix. | Role matrix, authentication flows, log events, retention, and security test authorization are not provided. This is not a penetration test. |
| NFR-03 — Scalability (local ID) | High visitor volumes without performance loss | Plan scalability testing only after expected visitor volumes, traffic profile, service limits, and environment are agreed. | No numeric workload or acceptable degradation threshold is supplied. |
| NFR-04 — Data privacy (local ID) | GDPR, CCPA, and regional data policies | Plan privacy-focused checks against approved data handling, consent, access, retention, and deletion requirements, if supplied. | Jurisdiction-specific obligations, data flows, retention rules, and evidence of compliance are not provided. Testing does not establish legal compliance. |
| NFR-05 — Reliability (local ID) | 99.9% uptime SLA for enterprise customers | Plan review of availability evidence and, if requested, appropriately scoped reliability/monitoring checks. | A short QA cycle cannot establish an uptime SLA. Measurement window, exclusions, and monitoring evidence are not provided. |

### User-flow coverage

- **A/B test setup:** define hypothesis and target metrics; select an audience; configure variations; launch and monitor; review SmartStats results and conclude a winner. Coverage is conditional on confirmed workflow states and statistical acceptance rules.
- **Behavioral analysis:** access Insights; generate heatmaps, recordings, and funnels; correlate findings with test outcomes; prioritize optimization ideas. Coverage is conditional on available data, consent, and product configuration.

Success metrics in the PRD (conversion rate, experiment velocity, engineering time, personalization engagement, and NPS) are business outcome measures. They are not assigned pass/fail thresholds in this plan; thresholds and measurement methods require stakeholder agreement.

## 5. Test Approach, Levels, and Types

### Approach

Use a risk-based, requirements-traceable approach. Prioritize Must requirements (FR1–FR4 and FR6) and dependencies that can invalidate test results, such as audience data, integrations, experiment metrics, and SmartStats calculation rules. Treat High and Medium requirements as planned coverage, subject to release scope and readiness.

For each approved requirement, derive cases only after acceptance criteria, observable outcomes, and relevant configuration are confirmed. Use synthetic or approved data. Record unverified expectations as questions or assumptions for review, not as product facts.

### Test levels

- **System/feature testing:** assess user-visible workflows for experiments, insights, personalization, reporting, and program management.
- **Integration testing:** assess approved connectors and data exchange using sandbox or non-production endpoints where available.
- **Regression testing:** rerun approved critical workflows after relevant changes; maintain a regression subset based on risk and usage.
- **Cross-browser/device testing:** cover the product-supported browser/device matrix after it is supplied. The PRD calls for cross-device/cross-browser QA but does not identify supported targets.

### Test types

- Functional positive, negative, and boundary testing where behavior is defined.
- Exploratory testing for workflows with incomplete acceptance criteria, with observations distinguished from requirement-based failures.
- Data integrity and reporting reconciliation for approved metrics and integrations.
- Performance testing for the 2-second editing target and scalability only with agreed workloads and acceptance thresholds.
- Security-control checks for 2FA, role-based permissions, and activity logs within approved access and authorization.
- Privacy-focused verification only against supplied and approved privacy requirements.
- Reliability/availability evidence review; extended reliability testing requires separate scope and a defined measurement window.

Automation framework, programming language, test management platform, and tooling are **Not provided**. Select tools after the target environment, integration method, and team standards are confirmed.

## 6. Environment, Tools, Access, and Test Data

### Environment

- PRD URL: https://app.vwo.com/
- Environment type (production, staging, or test): **Not provided**. The URL is not confirmed as a safe test environment.
- Tenant/account, build/version, feature flags, and configuration: **Not provided**.
- Do not run tests against a live/production tenant without explicit authorization and suitable safeguards.

### Access and roles

Required test accounts, provisioning process, role matrix, 2FA setup, and integration permissions are **Not provided**. Obtain least-privilege accounts for applicable user roles before testing. Do not place credentials in test plans, source code, logs, or reports.

### Test data

Use synthetic or approved data for experiments, variations, audience attributes, analytics events, recordings, personalization content, and connector payloads. Data sets, reset procedures, consent configuration, and expected metric values are **Not provided** and must be agreed before execution.

### Tools and dependencies

Test management, defect tracking, browser/device lab, monitoring, performance tooling, connector sandboxes, and reporting access are **Not provided**. Confirm availability and ownership before test execution. Integration testing depends on approved connector scope and non-production credentials/endpoints.

## 7. Entry and Exit Criteria

The criteria below are proposed for review. They are not approved release gates unless stakeholders accept them.

### Proposed entry criteria

- Test scope and release/build under test are identified and approved.
- Detailed acceptance criteria, expected outcomes, and requirement-to-test traceability are reviewed for the selected features.
- Approved non-production environment, tenant, access, and role accounts are available and smoke-checked.
- Test data, reset procedures, consent requirements, and integration sandboxes are available where applicable.
- Supported browsers/devices and applicable service limits are agreed.
- Performance, scalability, privacy, and reliability thresholds and measurement methods are agreed before those test types begin.
- Defect reporting and escalation contacts are identified.

### Proposed exit criteria

- All in-scope approved requirements have mapped test coverage, with exclusions and unresolved gaps documented.
- All planned critical/high-priority tests have an execution status and result recorded when execution is authorized.
- No open Critical or High severity defects remain for the release scope, unless explicitly accepted by the accountable product/release owner. Severity definitions and acceptance authority require agreement.
- Other open defects have documented impact, disposition, owner, and target resolution/review date.
- Applicable performance and integration results meet their approved thresholds; no thresholds are inferred from this plan.
- Test summary, residual risks, deviations, and approval are recorded.

No test execution has been performed as part of authoring this plan.

## 8. Roles, Responsibilities, Estimates, and Schedule

| Role | Responsibility | Assignment / estimate |
| --- | --- | --- |
| Product owner / product manager | Confirm scope, business rules, acceptance criteria, priorities, and residual-risk decisions. | Name and availability: Not provided. |
| QA lead / test planner | Maintain this plan, traceability, readiness, reporting, and test completion summary. | Owner and estimate: Not provided. |
| QA engineers | Design and execute approved tests; record evidence and defects. | Team size and estimate: Not provided. |
| Engineering / integration owners | Explain technical behavior, provide builds, support triage, and enable approved environments/connectors. | Contacts and availability: Not provided. |
| Security / privacy stakeholders | Approve security/privacy scope and review relevant findings. | Owners and approval process: Not provided. |
| Operations / platform owners | Provide monitoring, performance constraints, and availability evidence where applicable. | Owners and availability: Not provided. |

Schedule, milestones, effort estimates, and release dates are **Not provided**. Estimate only after scope, environment readiness, test data, and integration dependencies are confirmed.

## 9. Defect Management and Reporting

Use the team's approved defect-tracking system; the tool is **Not provided**. Each defect should include a concise title, affected requirement, environment/build, preconditions, reproducible steps, expected and actual results, evidence, impact, and reproduction status. Do not include secrets or personal data in defect evidence.

Severity and priority conventions, triage attendees, response targets, and reporting cadence are **Not provided** and require agreement. Proposed triage should classify defects by user/business impact, affected requirements, reproducibility, and available workaround. Report coverage, execution status, open defects, blocked tests, assumptions, and residual risk at an agreed cadence.

## 10. Risks, Dependencies, Assumptions, and Open Questions

### Risks and dependencies

- High-level PRD language may result in ambiguous expected results, especially for SmartStats, “real-time” reporting, targeting, and personalization.
- Missing environment and tenant details could prevent safe, representative testing.
- Integrations depend on enabled products, credentials, test endpoints, data mappings, and representative synthetic data.
- Behavioral insights depend on event capture, consent/privacy configuration, sampling, and data availability.
- The 2-second target and “high visitor volumes” lack workload and measurement definitions.
- A 99.9% uptime SLA cannot be validated with a short functional test cycle alone.
- Privacy and security checks require approved policies, role definitions, data handling rules, and authorization.

### Assumptions

- The product name is VWO and the PRD URL is https://app.vwo.com/; “VMO.com” is not used as the product identity because it differs from the supplied PRD.
- FR1–FR9 are source requirement IDs. NFR-01 through NFR-05 in this plan are locally assigned traceability IDs.
- All non-production test access and data will be explicitly approved before execution.
- Proposed entry/exit criteria are suggestions pending stakeholder approval.

### Open questions

- Which release, build, modules, and user journeys are in the immediate test scope?
- What detailed acceptance criteria and expected metric/statistical results apply to each requirement?
- Is there an approved non-production tenant? What are its URL, build/version, and supported configurations?
- Which browser/device and integration matrices are supported and required for this release?
- Which user roles, permissions, 2FA flows, audit events, and account setup are required?
- Which integrations are enabled and in scope, and what sandbox endpoints/data contracts are available?
- What event, consent, masking, retention, deletion, and privacy rules apply to behavioral data?
- What workload, percentile, measurement window, and pass thresholds define performance and scalability acceptance?
- What availability evidence and measurement period are used to assess the 99.9% SLA?
- Who owns test approval, defect triage, schedule, and residual-risk acceptance?

## 11. Suspension and Resumption Criteria

### Proposed suspension criteria

Pause affected testing when the environment is unavailable or unstable; the build changes materially during a test cycle; test data or integrations are unreliable; access is unauthorized or exposes production data; expected behavior is too ambiguous to judge; or a critical defect makes further testing unsafe or invalid. Security/privacy activity must also pause if authorization or handling requirements are unclear.

Record the reason, affected scope, current status, evidence, and decision owner. Continue unaffected testing only when it remains valid and approved.

### Proposed resumption criteria

Resume after the responsible owner confirms the blocking issue is resolved; environment/build and test data are stable; required access and authorizations are restored; affected cases are reviewed for impact; and the QA lead and relevant stakeholders agree that results will be valid. Re-run impacted checks as appropriate and record any regression scope.

## 12. Test Deliverables and Approval

### Planned deliverables

- Approved test plan and change history.
- Requirement-to-coverage mapping and approved test designs in the team's selected test management format.
- Execution evidence and defect records, if execution is separately authorized.
- Test summary with coverage, results, deviations, unresolved risks, and recommendation, if execution occurs.

This document is the only deliverable created in this step. Test cases, automation, and execution evidence are not included.

### Approval

| Role | Name | Decision | Date |
| --- | --- | --- | --- |
| Product owner / delegate | Not provided | Pending | Not provided |
| QA lead | Not provided | Pending | Not provided |
| Engineering / release representative | Not provided | Pending | Not provided |

Approval of this plan does not authorize testing against production or grant access to VWO. Environment and execution authorization must be handled separately.
