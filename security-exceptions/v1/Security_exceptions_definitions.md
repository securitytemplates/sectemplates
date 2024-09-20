# Security Exceptions Definitions


## About
This document defines 
 * Common terminology used in the exceptions process
 * Outlines the roles of the various stakeholders involved
 * Provides a sample stakeholder approval table


## Contents
- [Security Exception Levels](#security-exception-levels)
- [Program Roles](#program-roles-and-responsibilities)
- [Program Terminology](#program-terminology)
- [Security Exception Approval Table](#Security-exception-approval-table)
- [Additional References](#additional-references)

## Security Exception Levels
A straightforward approach to classifying the level of a security exception is to reuse the vulnerability level or rank associated with the finding. This is typically defined within a vulnerability management program. Example classification systems <a href="https://github.com/securitytemplates/sectemplates/blob/main/vulnerability-management/v1/Vulnerability_management_definitions.md">can be found here</a> in the <a href="https://www.sectemplates.com/2024/08/announcing-the-vulnerability-management-program-pack-10.html">vulnerability management program</a> pack. 

## Program Roles and Responsibilities
This section outlines the various roles involved in the exception process, and provides context for what their duties are.

<b>Security Exception Program Owner: </b>
  * <b>Definition:</b> The exception program owner oversees the program and provides oversight for all company-wide issues.
  * <b>Duties:</b>
    * Ensures that issues are effectively communicated to risk owners, and risk approvers.
    * Serves as the escalation point for the process and specific issues.
    * Provides oversight and support for subject matter experts.
    * Coordinates and leads security exceptions meetings.
    * Manages metrics and reporting.
 
<b>Risk Owner:</b> 
  * <b>Definition:</b> The risk owner is responsible for the risks identified in their products, services, or processes, and is accountable for either remediating or managing those risks.
  * <b>Duties:</b>
    * Serves as the point of escalation when remediation cannot be completed within the policy or guidance SLAs.
    * Owns the prioritization of risks within their area of responsibility.
    * Accountable for the identified risk. 
    
<b>Risk Approver:</b> 
  * <b>Definition:</b> A risk approver consists of one or more senior leaders responsible for overseeing risk decisions and the plans developed by risk owners. Ultimately, the risk owner's leadership is accountable and MUST play a role in the organization's risk decisions.
  * <b>Duties:</b> 
    * They hold the ultimate authority to approve risk acceptance or remediation plans proposed by the risk owner and subject matter experts.
    * Examples include the Chief Information Security Officer (CISO), Chief Technology Officer (CTO), Chief Product Officer (CPO), Chief Legal Officer (CLO), and Chief Operating Officer (COO).

<b>Subject Matter Expert:</b> 
  * <b>Definition:</b> Subject Matter Experts (SMEs) are technical advisors specializing in risk identification, classification, and remediation. SMEs may include security engineers/analysts/architects, security consultants or vendors, software engineers or leads, site reliability engineers (SRE), or security and engineering leadership.
  * <b>Duties:</b>
    * Communicate the impact of risks to the company’s stakeholders and customers.
    * Serve as technical experts who can discuss risk-related concerns at all levels.
    * Develop mitigation plans, including alternative solutions.

## Program Terminology

<b>Risk Level</b>
* The level of risk an issue presents to the company, its customers/partners, its environment/data, and external public perception. Ideally, this should align closely with your <a href="https://github.com/securitytemplates/sectemplates/blob/main/vulnerability-management/v1/Vulnerability_management_definitions.md">vulnerability ranking methodology</a>.

<b>Compensating Control</b>
* The NIST definition is going to be used here "A management, operational, and/or technical control (i.e., safeguard or countermeasure) employed by an organization in lieu of a recommended security control in the low, moderate, or high baselines that provides equivalent or comparable protection for an information system." - NIST [[2](#additional-references)]

<b>Vulnerability Management Program</b>
 * A VM program [[1](#additional-references)] defines risk levels, and remediation SLAs for identified risks in a company.
 * <b>Note:</b> Your Security Exceptions program should align closely with these definitions to ensure consistency, otherwise you may be flagged with an audit finding by a QSA during an audit. 

<b>Risk Treatment Plan/Remediation Plan</b>
 * A risk treatment plan outlines options and the desired path forward for mitigating or resolving a risk.

<b>Residual Risk</b>
  * This represents the remaining risk of a security issue after mitigating controls, hardening, or other partial remediation efforts have occurred. For example, a critical issue may be lowered to a medium level if the exploitability shifts from "very easy" to "very hard" as a result of additional hardening or controls implemented.

<b>Impact</b>
  * This defines the worst outcomes that can happen to the company, its customers/partners, its environment/data, and external public perception. This includes financial considerations, public relations concerns, contractual violations, and regulatory violations.


## Security Exception Approval Table 
It is critical to set clear expectations regarding who is authorized to accept risk at your company (risk owner) and who has the authority to overrule a risk decision (risk approver). By creating a table of approvers based on risk level, you can quickly identify who needs to be involved in a consistent and repeatable manner. Below is a sample approval table that you can utilize in your exceptions program.

| Vulnerability severity | Default time to remediate | Product/Engineering risk approver| Security team risk approval for extension| Guidance for extension without escalation|
|-----------------------|---------------------------|---------|-----------|-------------|
| Critical| 0-7 days | Product/Engineering VP/C-suite | Security VP/CISO| Criticals can only be extended for ~2 hours without escalation|
| High | ~30 days| Engineering/Product director | Security director | Highs can only be extended for 1-2 days without escalation|
| Medium | ~60 days | Engineering manager | Security manager | Mediums can only be extended for ~10 days without escalation|
| Low |  ~90 days | None required | Sr/Staff security engineer/analyst| Lows can only be extended for ~20 days without escalation|

The "Guidance for Extensions Without Escalation" column outlines the rules for the security exceptions program owner or security subject matter expert to approve extensions without fully engaging in the security exceptions process. Timelines beyond this criterion would require the creation of a security exception.

<b>Note: </b> The 'Default Time to Remediate' section should align with your <a href="https://github.com/securitytemplates/sectemplates/blob/main/vulnerability-management/v1/Vulnerability_management_definitions.md">vulnerability SLAs</a>. 


## Additional References
[1] SecTemplates Vulnerability Management Program Pack <br>
[https://www.sectemplates.com/vulnerability-management/](https://www.sectemplates.com/vulnerability-management/) <bR><br>
[2] NIST Definition 'compensating security control' <br>
[https://csrc.nist.gov/glossary/term/compensating_security_control](https://csrc.nist.gov/glossary/term/compensating_security_control)<br><br>

Document version 1.0 copied from [Sectemplates.com](https://www.sectemplates.com) 2024
