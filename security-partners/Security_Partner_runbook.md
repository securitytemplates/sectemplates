# Security Partner runbooks

# About
This document outlines a set of standard procedures for supporting engineering, operations, and product teams by a security engineer/partner.

<b>Note:</b> Please see the <a href="./Security_partner_preparation_checklist.md">security partner preparation checklist</a> for steps on how to set up a program prior to using this document.


## Contents
- [Plug into engineering and product](#plug-into-engineering-and-product)
- [Review "Product Requirements Documents" (PRDs)](#review-product-requirements-documents-prds)
- [Review "Technical Design Documents" (TDDs)](#review-technical-design-documents-tdds)
- [Sheparding stakeholders to other security processes](#sheparding-stakeholders-to-other-security-processes)
- [Monitoring security scanning health](#monitoring-security-scanning-health)
- [Security vulnerability remediation assistance](#security-vulnerability-remediation-assistance)

## Plug into engineering and product
See the section '<b>Security partner preparation steps</b>' in the <a href="./Security_partner_preparation_checklist.md">preparation guide</a> to properly integrate into product and engineering workflows.  

## Review Product Requirements Documents (PRDs)
To properly evaluate the security posture of an application, start with the PRD, which defines the goals and objectives for a particular product or feature release. This document focuses more on the 'What', whereas the TDD focuses more on the 'How'. By engaging early, you can identify risks through a security design review or threat model and propose solutions before a single line of code is written. Addressing these issues during the PRD phase is the most cost-effective and efficient way to close security gaps, and avoid disruptions during release planning. 

This process involves adding comments to documents and scheduling a meeting with the PRD authors to ensure that what is written accurately reflects what engineering should build. You should:
* <b>Review the document</b> - Carefully review every line, add comments, and seek clarification. If data flow diagrams, other critical contextual information, or key sections necessary for a security design review are missing, flag them now. Tag items that prevent you from completing the review to properly set expectations.
* <b>Schedule a design review meeting with the PM and eng team (product focused security design review)</b> - Request that the product manager and engineering team walk you through the entire application and workflow. Here, you can seek clarification and may also discover that certain aspects are loosely defined, leaving room for engineering to interpret them differently.
* <b>Request updates</b> - After your 'product focused security design review' meeting, you will likely have questions requiring updates. Ensure you send out a list of action items following the review, with clear expectations on why completing these tasks is important.
* <b>Identify changes</b> - Ensure that any required changes are properly documented in the PRD. Create tickets for follow-up items with clear prioritization, categorizing them as:
  * Must be fixed before release
  * Must be fixed quickly after release
  * Should be fixed in future releases<br><br>
This is crucial to ensure that priorities are clearly understood by both the product and engineering teams, as well as any other security stakeholders involved.

<b>Note</b>: You will often find discrepancies between the PRD, TDD, and what is discussed during a product or feature walkthrough in a design review meeting. This is why reviewing both documents, and meeting with the teams is essential.

## Review Technical Design Documents (TDDs)
Ideally, you will have reviewed a PRD in advance. However, there may be cases where a PRD is unavailable or you have been brought in later in the process. If a PRD exists, review it first to understand the business goals and release timeline. Once you have this context:
* <b>Review the TDD</b> - This document should specify how an engineering team plans to build the desired functionality. Ensure that it includes data flow diagrams, details on the data being processed (e.g. PII), and clear documentation of third-party integrations. Additionally, verify that all planned functionality supporting the feature is outlined. In some cases, details may be missing and should be clarified during a security design review session with engineering. 
* <b>Deep dive the TDD with eng (eng focused security design review)</b> - This meeting should primarily focus on 'how' things are being built and may not require the product manager to attend. The discussion should identify security requirements, missing security controls, and guidance on safely implementing the desired functionality. This may include referencing internal developer security guidelines or policies, if available.
* <b>Request updates</b> - After your TDD focused security design review meeting, you will likely have questions that require updates. Ensure you send out a list of action items following the review, with clear expectations on why completing these tasks is important for the security review.
* <b>Identify changes</b> - Ensure that any required changes are properly documented in the TDD. Create tickets for follow-up items with clear prioritization, categorizing them as:
  * Must be fixed before release
  * Must be fixed quickly after release
  * Should be fixed in future releases<br><br>
This is crucial to ensure that priorities are clearly understood by both the product and engineering teams, as well as any other security stakeholders involved.

<b>Note</b>: You will often find discrepancies between the PRD, TDD, and what is discussed during a product or feature walkthrough in a design review meeting. This is why reviewing both documents, and meeting with the teams is essential.


## Sheparding stakeholders to other security processes
Given your subject matter expertise you are uniquely qualified to know when something smells fishy, or may need additional security team support. For example:
* <b>Privacy concerns:</b> When data is being collected, shared, or when existing data access changes, there may be privacy considerations. Connect your engineering team with the privacy team's processes at your company and encourage them to engage early.
* <b>Vendor usage:</b> Teams may need to leverage third-party software, third-party integrations, or third-party data as part of their application's functionality. Support your engineering teams by integrating them into your company's Vendor Security process early.
* <b>Compliance concerns:</b> Questions regarding data storage regulations, physical locations for storing or hosting customer data, or policy-related matters should be directed to your compliance team.

## Monitoring security scanning health
As an AppSec expert, you have a deep understanding of how security scanners operate and how they are configured. You will need to periodically review each scanner to:
* <b>Verify configuration of each scanner type</b>: Ensure that SAST, SCA, Cloud, and DAST scanners are enabled, configured correctly, and running regularly against the product and code repositories.
* <b>Baseline scanner findings</b>: By establishing a baseline of scanner results, you ensure that the issues reaching engineering are valid and correctly prioritized.
* <b>Raise open vulnerabilities with the Engineering Manager</b>: If the EM is unaware of these findings, meet with them to share each issue, explain its significance, and collaborate on a process that enables them to address these issues independently rather than relying on the security partner.
* <b>Regularly review unremediated findings</b>: At this stage, the Engineering Manager should have a process in place for handling issues independently. However, it is still beneficial to periodically check in to determine if the team is facing resource or prioritization challenges that may be impacting its ability to address known risks.

## Security vulnerability remediation assistance
Engineering teams are responsible and accountable for ensuring that vulnerabilities are addressed in a timely manner according to internal <a href="https://www.sectemplates.com/vulnerability-management/">vulnerability management</a> SLAs. Most of the time, engineering and product teams are focused on other priorities and may not yet have a mature process for handling these types of issues. As a dedicated security expert, periodically review the board and assist engineering and operations by communicating important issues and helping them establish a routine for regularly reviewing these findings. Typically remediation assistance occurs in two ways: 
* <b>Engineering asking for help</b> - When there is a known security vulnerability, engineering may need assistance in finding a solution. This could involve identifying a suitable library or framework to mitigate the risk, providing specific code recommendations, or evaluating potential solutions that engineering is considering. One of the key responsibilities of a security partner is to support engineering in remediating such issues.
 
* <b>Guiding engineering on vulnerability burndown</b> - The security partner should have a clear understanding of the open risks affecting a supported team and must communicate effectively with the engineering manager about issues requiring prioritization. While the overall responsibility for oversight lies with the engineering manager, they may lack adequate dashboards or visibility into these issues. The security partner helps ensure that issues do not stagnate and provides the engineering manager with the necessary insights to monitor risks independently. Additionally, they guide the manager on when to seek technical assistance from the security partner.

Runbook version 1.0 copied from [Sectemplates.com](https://www.sectemplates.com) 2025
