# Bug Bounty Simplified Policy

## About
This sample policy is intended for modification and publication on your site or bounty page. <b>It is strongly recommended that you collaborate with your legal team to review and adjust this policy</b> according to your business needs <b>before publishing</b>.

## About this Program
<i>&lt; Insert an inspirational blurb about your company and its security goals. &gt;</i><br>

Example:<br>
Here at K-rad Industries, we are committed to protecting our customers and their data. As part of our overall security strategy, we welcome the contributions of external security researchers who find vulnerabilities to help us improve the security posture of our systems and customers. If you've discovered a security issue you believe we should be aware of, we'd love to work with you and reward you for your efforts. Our bug bounty program applies to vulnerabilities found in our in-scope systems and products outlined below. By working with us collaboratively and confidentially, you will be rewarded for your valid findings.<br>

## Program Rules
The following testing approaches and attacks are not allowed as part of this program:<br>
  * Exfiltration of data
  * Denial of service testing or attacks
  * Phishing
  * Attempting to obtain information from other user accounts. If you believe you've found an issue that may result in compromising the data or session of another user account, we ask that you utilize your own testing accounts in this situation.
  * Using automation to brute force login credentials
  * Manually or using automation to scrape large sections of this site to enumerate user IDs, usernames, emails, or other user/employee information

## Testing Account Rules
Prior to performing testing on the site, you must observe and agree to the following rules:
  * Attempts to gather information from an account other than the account being used should be limited to accounts you control. You may not at any time attempt to gather information from an account you do not directly own. If you want to test gathering information or escalating to another user, please create one account for each of these purposes. 
  * Please create testing accounts with 'bugbounty' in the username, for example, 'DanKam-bugbounty,' to clearly indicate your account is bug bounty-related. This helps us troubleshoot possible issues resulting from the testing you are performing.

## Safe Harbor
We are not lawyers, we recommend reviewing <a href="https://www.microsoft.com/en-us/msrc/bounty-safe-harbor">Microsoft's bug bounty safe harbor language</a> and consult with your legal team. 


## Bounty Eligibility 
 * You agree to the rules, terms, and conditions set forth in this document.
 * You are not on a U.S., UK, or EU list of sanctioned individuals.
 * You are not a current employee, nor have you been an employee within six months prior to submitting a report.
 * You must be the first person to report this issue.
 * You will not attempt to access personal information belonging to another user, including by exploiting a vulnerability.
 * You will not perform attacks or security testing against vendors, partners, or third parties that may be in use.
    
## Bounty Scope
This section lists the assets, websites, products, and services that are considered in-scope and out-of-scope. This list is subject to change without notice and should be reviewed prior to submitting a finding.<br>

<b>Assets in-scope</b><br>
  * *.sample.net
  * sso.sample.net
  * Mobile application
  * Desktop application

 <b>Assets out-of-scope</b><br>
  * cdn.sample.net
  * images.sample.net

<b>Vulnerabilities out-of-scope</b><br>
  * HTTP TRACE, TRACK, or OPTIONS methods enabled
  * Non-exploitable clickjacking findings such as pages missing X-Frame-Options, which are not exploitable  
  * Bugs that represent no security risk
  * Cross-site request forgery with minimal or no security impact
  * Denial of service attacks/weaknesses
  * Generic best practice concerns without demonstrable exploitation
  * Normal bugs that have no security implications
  * Credential stuffing and account takeover
  * Spam or social engineering methods
  * Password complexity-related concerns
  * Mobile application crashes that do not lead to a security escalation or abuse
  * Vulnerabilities requiring jailbroken devices
  * Vulnerabilities requiring physical access to an unlocked device to exploit

 If you believe you've found an issue that affects an asset belonging to us but isn't included in the scope here, please contact us.

## Reward Amounts
A table indicating the payout amounts by severity, with examples, provides researchers with the right expectations. A sample table is included below:

  | Severity     |  Bounty amount    | Example issues|
  |----------|----------|----------------------------|
  | Critical  | $10,000| PII disclosure, remote command execution, SQL Injection, code injection, total authorization or authentication bypass (e.g. IDOR), admin/root escalation|
  | High  | $5,000| Cross site scripting, SSRF, partial authorization or authentication bypass |
  | Medium  | $2500| Directory traversal, cross-site request forgery, missing secure cookie flags on session cookies|
  | Low  | $250 | Minor information disclosure, missing httponly cookie flags|


## Reward Rules
We reserve the right to pay you for findings you've submitted to us. As part of this agreement, you will not disclose an issue prior to a remediation being deployed and not without receiving prior authorization to disclose the issue. Failing to abide by these rules may result in a ban from this program or other disciplinary actions.

## How to Submit Your Report
If our security team is unable to reproduce your issue and verify its validity, a bounty cannot be awarded. We ask that each submission contains the following details:

1. Description of your finding.
2. Detailed steps to reproduce your finding.
3. Account name used to perform the testing, when applicable. This information enables us to verify account-specific states, which can help troubleshoot the issue, including the user role type (e.g., user, manager, collaborator, admin).
4. A description of the impact on our environment, customers, data, or employees.
5. A screenshot, video, or proof of concept code to enable us to reproduce the issue.
6. The web browser version or 'User-Agent' you used during testing. This may impact the endpoint or workflow.
7. (When applicable) Software versions and operating systems impacted.

If you've found something but aren't sure if it's eligible, please reach out to us.

## Frequently Asked Questions
<i>&lt;This section will need to be filled out and published prior to the launch of your bounty, and continuously updated based on your program's growth. &gt;</i>

## Legal Disclaimer Before Using this Document
Given that this is a policy and publicly represents your company's position, you need to have this reviewed by your legal and compliance teams. Failure to have the appropriate internal legal/compliance stakeholders review this could result in compliance or legal consequences.

Policy version 1.0 copied from [Sectemplates.com](https://www.sectemplates.com)
