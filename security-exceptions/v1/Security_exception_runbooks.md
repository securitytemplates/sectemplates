# Security Exception Runbooks 

# About
This document outlines a set of standard procedures for handling a security exception. Security exception program owners, risk approvers, and supporting security staff (subject matter experts) should utilize these runbooks to facilitate consistent approachs for handling/supporting exception requests. 
Please see the <a href="./Security_Exception_preparation_checklist.md">security exception preparation checklist</a> for steps on how to set up a program prior to using this document.

## Contents
 - [Security exception support steps](#Security-exception-support-steps) - Performed by supporting security staff
 - [Security exception approval/rejection steps](#Security-exception-approval-and-rejection-steps) - Performed by risk owner/risk approvers
 - [Security exception intake steps](#Security-exception-intake-steps) - Performed by security exception program owner
 - [Security exception reoccuring meeting steps](#Security-exception-reoccuring-meeting-steps) - Performed by security exception program owner

# Security exception support steps
<b>Role performing this step:</b> Security subject matter expert

This runbook is used by a subject matter expert within security, typically a security engineer, architect, or analyst who identified the risk, when assisting stakeholders transitioning their vulnerability into an exception request.

1. <b>Stakeholder support requested:</b> The software engineer, engineering manager, or engineering leader has communicated a desire to either not fix the issue or delay the fix. This may have occurred in the vulnerability ticket, on Slack, or during a meeting/conversation about the issue. 
2. <b>Evaluate technical solutions with stakeholders:</b> Sometimes the request from engineering to delay or not fix an issue is due to a lack of understanding of how to resolve it.
      * As a first step, work with your software engineer and engineering manager counterparts to determine 1-3 possible fixes.
      * Identify and prioritize the ideal/preferred solution, and determine a 'Plan B,' outlining the pros and cons of each option. This is critical for helping the engineering manager and software engineer understand whether one path is acceptable or may require more overall work.
3. <b>Propose the preferred solution to decision-makers in engineering:</b> Attempt to coordinate with the risk owner along with the engineers involved in developing the solutions from the previous step. Collaboration and alignment between the two teams are critical for influencing and prioritizing the chosen path forward.
      * Be prepared to discuss the pros and cons of the proposed solution, as well as Plan B.
      * <b>Note:</b> Failure to prepare adequately may result in being sent back to the drawing board and could lead to a loss of trust between security and engineering.
   
4. <b>Determine if an exception is required:</b> If, after collaborating on alternative solutions, a determination is made to delay the risk treatment or accept the risk, you will need to evaluate the next steps.
      * If an extension is requested, review the <a href="./Security_exceptions_definitions.md#Security-exception-approval-table">risk extension table</a>. This will guide you on whether you can approve an extension based on the "<b>Guidance for extension without escalation</b>" column.
           * If the request for delay is within thresholds and you are comfortable with it, update the vulnerability ticket with a comment explaining why you are okay with extending the issue. This is critical for audit purposes.
           * If the request for delay is within thresholds, but you are not comfortable with it, proceed to the next step.
           * If the request for delay is not within thresholds, proceed to the next step.
     * If a request for acceptance of the risk is made, proceed to the next step.
5. <b>Help route stakeholders to exceptions process when remediation alignment cannot be met:</b> Direct them to the process for filing an exception request, either by creating an exception ticket or utilizing a document template. This will follow the chosen path outlined in the <a href="./Security_Exception_preparation_checklist.md">preparation checklist</a>. 
6. <b>Assist the risk owner/team with the exception details:</b> After the risk owner or their team has filled out the exception request, review it to ensure each field is complete and accurately describes the risk. It’s important to 'audit' the content, as the risk owner may have an incentive to downplay the risk. At the same time, you must accurately describe the risk level after considering the engineers' data points and perspectives.

# Security exception approval and rejection steps
<b>Role performing this step:</b> Risk owner

This runbook is used by the risk owner to evaluate, approve, or reject an exception sent to them by SMEs within securty and their organization. 

1. <b>Review exception request</b>: 
   * If the request is unclear or lacks necessary details, return it to the subject matter experts for clarification or additional information.
   * If the request contains all the required information, ensure that the "Pros and Cons" section accurately reflects the implications of approving the exception. Make any adjustments as needed.
2. <b>Determine exception type:</b>
   * You will need to determine if you want to delay fixing the issue, or if accepting the risk and not fixing it is the preferred option.
   * Once you have made your decision, update the exception ticket/document to reflect the chosen outcome.
3. <b>Decide upon acceptance or rejection:</b> 
   * <b>Approving the exception:</b>
     * If the exception aligns with your desired outcome, update the approval section with the date of your approval.
     * Additional approvals may be required depending on the level of risk. This could involve your direct leadership team as well as security leadership.
   * <b>Rejecting the exception:</b>
     * As the risk owner, if you decide to move forward with remediation within SLA, after reviewing the details, you can cancel the exception process and simply prioritize the fix.
     * If using a ticketing system, ensure that you or a member of your team adds a comment indicating plans for remediation or cancellation of the exception for audit purposes.


# Security exception intake steps
<b>Role performing this step:</b> Security Exception Program Owner

This runbook is designed to help the security exception program owner with supporting, and evaluating incoming exceptions. 


1. <b>Security exception request is recieved from risk owner</b>: Ensure that the individual requesting the extension is authorized to do so. This is typically a product manager, engineering manager, or a delegated engineering lead.
    * The request may come through Slack or another communication channel.
    * Ask the appropriate risk owner/requestor to complete the security exception ticketing workflow and clearly state whether they wish to delay the fix or accept the risk. This process should result in either a new exception ticket or document, depending on the procedure outlined in the <a href="./Security_Exception_preparation_checklist.md">preparation checklist</a>.
2. <b>Evaluate request from risk owner</b>
    * Verify that the required fields are properly completed by the appropriate risk owner or delegate.
    * <b>Risk owner has communicated a desire to delay fix:</b> Determine if the delay is reasonable and does not require escalation to other stakeholders. Refer to the '<a href="./Security_exceptions_definitions.md#Security-exception-approval-table">Security Exceptions Approval Table</a>' for extensions that do not require escalation.
       * <b>If the extension delay is within the approved extension range</b> in the '<a href="./Security_exceptions_definitions.md#Security-exception-approval-table">Security Exceptions Approval Table</a>' ensure that the appropriate security approvers update the ticket to indicate approval.
         * Add a note stating that an exception is not required, and request that the vulnerability ticket be updated with the new fix date.
         * After verifying that the vulnerability ticket reflects the updated SLA, close the exception ticket.
       * <b>If the extension delay is outside of the approved extension range</b>  in the '<a href="./Security_exceptions_definitions.md#Security-exception-approval-table">Security Exceptions Approval Table</a>' proceed to the next step. 
    * <b>Risk owner has communicated to accept risk and not fix it:</b> It is possible that the risk owner is not fully aware of the issue, or that security has not explored alternative solutions. Engage the security SMEs responsible for remediation and technical guidance to verify sufficient support has been provided. This may include teams such as product security, SecOps, or InfraSec, depending on the nature of the identified risk.
      * After verifying the correct due diligence was performed, ensure that the risk owner has 'approved' the ticket, either through a comment or via the ticketing workflow status.
3. <b>Determine risk approvers</b>: Based on the 'Security Exceptions Approval Table,' you will need to tag the appropriate risk approvers from both security and non-security teams, either manually or via automation.
4. <b>Monitor exceptions and slack channel:</b> Risk approvers may have questions, so it is the risk owner's responsibility to provide answers. However, tickets or conversations may get lost, so providing oversight can help ensure things proceed smoothly.
    * For urgent issues, tag the appropriate people in the Slack channel for assistance and involve SMEs as necessary.
5. <b>Add items for discussion in reoccuring exceptions meeting:</b> When tickets require further discussion beyond Slack or ticketing, add the items to the recurring meeting.


# Security exception reoccuring meeting steps
<b>Role performing this step:</b> Security Exception Program Owner

This runbook is designed to help the security exception program owner facilitate an efficient meeting with the appropriate risk approvers, risk owners, and subject matter experts (SMEs).

1. <b>Ensure correct risk owners are invited to meeting</b>: Some attendees may have scheduling conflicts or may not have responded to the meeting invite. Be aware of who is unable to attend so that SMEs supporting the issue are not required to attend unnecessarily.
2. <b>Ensure the correct security subject matter experts are invited</b>: Building on the previous step, confirm that the appropriate SMEs are present to support the risk owners and approvers attending the meeting. This may include security, engineering, operations, or product personnel, depending on the issue.
3. <b>Start the meeting</b>: Self explanatory.
4. <b>Review open issues requiring action</b>: 
      * Extension requests
      * Risk acceptance
5. <b>Discuss, and address concerns by applicable stakeholders</b>: Stakeholders may ask questions related to technical aspects, impact, or accuracy. Provide support as needed, with the help of the relevant SMEs.
6. <b>Determine next steps and owners for each action item</b>: The meeting should conclude with a clear list of follow-up actions for each stakeholder, including the exception program owner. Sending the list of follow-up items in the meeting invite or via a dedicated Slack channel can help ensure nothing is overlooked. The level of follow-up or support you provide may vary depending on your preferred level of oversight.


Runbook version 1.0 copied from [Sectemplates.com](https://www.sectemplates.com) 2024
