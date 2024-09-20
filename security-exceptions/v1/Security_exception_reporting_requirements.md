# Security Exception Reporting Requirements 


## About
The goal of this document is to: 
  * Outline the minimum information required for a security exception ticket or document.
  * Suggest automation for security exception reporting to ensure that risk owners and approvers have an up-to-date understanding of issues requiring their attention.

<b>Note</b>: It is recommended  to first review the <a href="./Security_Exception_preparation_checklist.md">Security exception preparation checklist</a> to determine if a ticket, document, or hybrid approach will be used. 

## Minimum Information to Include in a Security Exception
Each security exception should include, at minimum, the following information: 
* <b>Title</b>: A precise description of the issue, avoiding vague or generic terms that may be overlooked.
* <b>Priority or Severity</b>: This should align with either your <a href="https://github.com/securitytemplates/sectemplates/blob/main/vulnerability-management/v1/Vulnerability_management_definitions.md">vulnerability ranking methodology</a> or a risk framework adopted by your company.
* <b>Assignee</b>: The individual responsible for addressing the issue.
* <b>Description of Issue</b>: A clear explanation of the vulnerability and its potential impact on the company, customers, data, and employees.
* <b>Pros and Cons of accepting the risk:</b> The risk owner and subject matter experts should complete both fields. Security should verify these details to ensure they are not presented more positively than the actual situation warrants.
* <b>Path required for technical uplift:</b> This should outline the effort and steps needed to address the risk as determined by the risk owner. This demonstrates that engineering has investigated and identified a solution rather than merely submitting an exception request without an identifed path forward.
* <b>Fix By Date</b>: This date should ideally align with adopted <a href="https://github.com/securitytemplates/sectemplates/blob/main/vulnerability-management/v1/Vulnerability_management_definitions.md">vulnerability remediation SLAs</a>.

<b>Note:</b> Some may prefer to have a separate field in Jira for each item listed above, while others might choose a combination of Jira fields and the rest under the description or in a separate attached/linked document. It's entirely up to you to decide what works best for your situation.

## Reporting Automation
In addition to ensuring that exceptions contain the required information, you will need to monitor the status of each issue. Generating useful reports keeps the security team and risk owners informed about issues that require attention. It is recommended to build automated reporting that provides weekly or bi-weekly updates to risk owners and offers support when they have questions. Most commonly, this automation sends emails or Slack messages to <a href="./Security_exceptions_definitions.md">risk owners</a> and approvers , clearly communicating items that require attention. This ensures issues do not fall through the cracks and that risk owners have an up-to-date view of the issues they are responsible for.

* <b>Expired security exceptions:</b> These issues should be flagged immediately to the appropriate risk owners, as they may not have had the opportunity to address them before expiration.
* <b>Security exceptions nearing expiration:</B> Communicating about exceptions nearing expiration provides visibility to risk owners, signaling that these issues need to be addressed.
* <B>Security exceptions requiring approval:</b> This flags exceptions that both require risk owner evaluation and response.

## Advanced Reporting Automation
Integrating security exception reporting with vulnerability reporting simplifies the number of reports sent to risk owners and allows one automation to handle both. Please see our vulnerability management program pack, particularly the <a href="https://github.com/securitytemplates/internal-sectemplates/blob/main/releasepacks/product-security/vulnerability-management/Vulnerability_reporting_requirements.md">vulnerability management reporting and automation</a>, for details on how these processes can work together.

Document version 1.0 copied from [Sectemplates.com](https://www.sectemplates.com) 2024
