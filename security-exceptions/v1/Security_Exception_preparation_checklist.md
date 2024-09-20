# Security Exception Preparation Checklist


## About
This document outlines the steps required to prepare for and establish a <a href="./">security exceptions program</a>.  For simplicity, we assume Jira is the bug tracking system in use due to its popularity.

## Contents
 - [Preparation steps](#preparation-steps) 
 - [Security Exception automation](#security-exception-automation)
   - [Automating exception reporting](#Automating-exception-reporting)
   - [Security exception health automation](#security-exception-health-automation)

## Preparation steps
- [ ] <b>Determine security exception program owner:</b> This individual will serve as a technical program manager to ensure smooth operations, handle escalations, and maintain follow-through.
- [ ] <b>Determine exception prioritization methodology:</b> To understand which security exceptions are higher priority, you will need to utilize a consistent approach to determine the priority. A simple approach is to reuse the priority of the vulnerability as it should capture the impact, existing mitigating controls, and severity levels. See the <a href="https://www.sectemplates.com/2024/08/announcing-the-vulnerability-management-program-pack-10.html">vulnerability management program pack</a> for details on <a href="https://github.com/securitytemplates/sectemplates/blob/main/vulnerability-management/v1/Vulnerability_management_definitions.md">vulnerability risk ranking methodologies</a>. 
- [ ] <b>Determine criteria and decision tree for approvals</b>: To enable teams to move quickly, provide a decision tree that specifies who should approve an exception based on its priority. A sample table <a href="./Security_exceptions_definitions.md">can be found here</a>.
- [ ] <b>Determine required details within an exception</b>:  Please see '<a href="./Security_exception_reporting_requirements.md">Security Exception reporting requirements</a>' for a list of specific fields to include in each exception request. 

- [ ] <b>Determine how to document/track exceptions:</b> You need to decide what type of artifact captures the exception details, such as a word document or Jira ticket. 
    * <b>Option 1 - Utilizing a word document for individual exceptions, and a spreadsheet for tracking all exceptions:</b> Some people prefer to stick with word documents and spreadsheets instead of integrating exceptions tracking into Jira. This pack provides a <a href="./Security_exception_template.md">sample exception template</a>, and <a href="./Security_exceptions_tracker.csv">exception tracker spreadsheet</a> to get you started.
      * <b>Pros:</b> You can get started quickly. 
      * <b>Cons:</b> Tracking the status of issues may be more manual, exception health automation/reporting automation may be limited.   
    * <b>Option 2 - Utilizing Jira ticketing and dashboarding:</b> Another option is to create new issuetype in jira using the <a href="./Security_exception_reporting_requirements.md">exception requirements specified here</a>.
      * <b>Pros:</b> Once setup correctly, you can easily create Jira dashboards to visualize the metrics/status' of your exceptions. Jira provides APIs that will enable both health automation and reporting automation. 
      * <b>Cons:</b> Initial setup is more work, and may require maintence occassionally. 
    * <b>Option 3 - Utilizing Jira ticketing with document attachment</b>: A hybrid approach.
      * <b>Pros:</b> You can automate exception reporting fairly easily. 
      * <b>Cons:</b> Automating ticket health reporting will be more challenging as it may require downloading and parsing the document template instead of jira fields. 
- [ ] <b>Develop a security exception runbook:</b> When an exception is filed or responded to by a risk owner, a standardized set of steps must be followed to ensure consistency. Sample runbooks <a href="./Security_exception_runbooks.md">can be found here</a>.
- [ ] <b>Test the workflow:</b> After implementing your desired approach, test every basic workflow including
    * Filling out the exception request to determine if additional/less fields are needed. 
    * Moving into a review state, then reverting back to the to-do/queue state.
    * Denying an exception/ticket
    * Approving an exception/ticket
    * Sending a ticket back for more information
- [ ] <b>Pilot the process:</b> Identify an appropriate risk item to test the process, and gather feedback from stakeholders. Incorporate this feedback to fix workflow issues, as well as to enhance the process. 
- [ ] <b>Develop ticket health automation to identify issues:</b> Automation is needed to verify that processes are running smoothly, tickets have the correct fields, and are not assigned to employees who have left the company. Please refer to the "[Security exception health automation](#security-exception-health-automation)" section below for more details.
- [ ] <b>Determine reporting requirements and capabilities</b>: After reviewing the <a href="./Security_exception_reporting_requirements.md">reporting requirements</a> and <a href="./Security_exceptions_metrics.md">metrics sections</a>, determine what metrics and reporting you want.
- [ ] <b>Develop reporting automation, and send out reports</b>: A weekly or biweekly report sent to risk owners who have issues to address provides visibility into unaddressed risks. Please refer to the "[Automating exception reporting](#Automating-exception-reporting)" section below for more details.
- [ ] <b>Establish slack channel to discuss exceptions:</b> Create an invite-only channel and include risk approvers and risk owners. This will enable faster communication, expedite responses, and support urgent escalations by bringing all relevant stakeholders together. 
- [ ] <b>Establish a regular exceptions review meeting:</b> Set up a biweekly or monthly meeting with approvers to address issues requiring their attention. Invite Risk Owners, Risk Approvers, and Subject Matter Experts to provide context during discussions. Please see the <a href="./Security_exception_runbooks.md">exception runbook section</a> for more information. 



# Security exception automation
This section will focus on two important aspects of a security exception program, reporting, and oversight of ticket health.


## Automating exception reporting
Please see <a href="./Security_exception_reporting_requirements.md">security exception reporting requirements</a> for this topic. 


## Security exception health automation
Verifying the quality of your tickets in an automated fashion is critical to ensure that risk is properly assigned to the correct owners, classified at the appropriate level, and not lost in the process. It is recommended to build automation that queries for these common quality issues and notifies the security DRI for your exceptions program daily: 
* <b>Tickets assigned to 'unassigned':</b> Tickets may be accidentally or intentionally assigned to 'unassigned,' and it's important to ensure these tickets are not lost.<br>
* <b>Tickets assigned to employee who have left the company:</b>  At some point, employees will leave the company, and tickets may remain assigned to them. It's important to flag these tickets promptly and reach out to their former manager to determine who the new owner should be. <br>
* <b>Tickets lacking a due date:</b> For various reasons, this field may become blank. Each ticket should have a clear expected fix-by date for the risk owner to evaluate.<br>
* <b>Tickets which have had their priority downgraded:</b> These tickets should be reviewed by the <a href="./Security_exceptions_definitions.md">security exception program owner</a> or their delegate to determine if the decision to lower the severity/priority was appropriate. <br>
* <b>Due dates changed:</b> People may attempt to change due dates to circumvent SLA oversight. It is recommended to mark this field as read-only; however, if you are unable to do so, you should monitor this field and notify the security team when the date is changed.<br>
* <b>Tickets which have had their priority increased:</b> These tickets should be promptly reviewed to determine if an urgent matter, possibly requiring a <a href="https://www.sectemplates.com/incident-response/">security incident</a> response, needs to be addressed. It also provides a signal on tickets which, during the transition to a higher priority, could be automatically considered out of SLA.

<b>Note:</b> If possible, tying a single report for both security exceptions and vulnerability oversight may be advantageous. Please see the '<a href="https://github.com/securitytemplates/sectemplates/blob/main/vulnerability-management/v1/Vulnerability_reporting_requirements.md">Vulnerability Management Reporting Automation</a>' section of the '<a href="https://www.sectemplates.com/vulnerability-management/">Vulnerability Management Program</a>' pack. 
<br><br>
Checklist version 1.0 copied from [Sectemplates.com](https://www.sectemplates.com/) 2024


