# Bug Bounty Runbook

## About
This runbook should be used once a bug bounty program has been established. Please see the <a href="./Bug_bounty_preparation_checklist.md">bug bounty preparation checklist</a> for steps on how to set up a program prior to using this document. 


## Bug Bounty Operation Steps
When a vulnerability report enters your review queue, perform the following steps:

1. <b>Vulnerability report is received from the security researcher and enters the triage queue</b><br>
   * When the bug bounty provider performs the initial triage of the issue, they will handle this first touch step.<br>
   * When you are directly evaluating the vulnerability report, it enters your review queue. <br>
2. <b>Attempt to reproduce the issue</b><br>
   * When there is not enough information to reproduce the issue, request additional details from the vulnerability researcher.<br>
   * When there is enough detail to reproduce the issue, perform the steps to evaluate if the issue is real using a test account. <br>
   * If the issue submitted is out of scope or invalid, contact the researcher and let them know. Occasionally, researchers may become frustrated or threaten retaliation. When this occurs, it's important to align with your security leadership, PR, and legal teams to respond accordingly.
3. <b>Determine impact to the company, services, employees, and customers</b><br>
   * If the issue appears to be invalid, contact the researchers and invite them to resubmit with additional details. <br>
   * If the issue appears to be real or valid, confirm the possible negative impact reported by the researcher, and loop in engineering stakeholders to verify the impact is correctly understood. This may require engaging engineering or ops on-call to assist. <br>
      * <b>For High-Critical severity issues</b>, spin up an incident channel per your <a href="https://www.sectemplates.com/2024/06/announcing-the-incident-response-program-pack-10.html">incident response process</a> to discuss the issue with applicable stakeholders and roll out a fix quickly. <b>If data leakage  potentially occurred, you MUST contact your incident response team and support them in forensic investigations. It's critical to determine how long the issue was open and if other researchers or attackers may have exploited the flaw. If data leakage is thought to have occurred, work with your incident response team to notify your legal team appropriately.</b><br>
      * <b>For Low-Medium severity issues</b> with a low impact, file the issue in your internal bug tracker and notify the issue owner.<br>
      * <b>For out of scope issues</b> that appear valid but are technically out of scope, evaluate with your team if the issue should still be paid out or if the asset containing the vulnerability should be added to the 'in scope' section of your <a href="./Bug_bounty_simplified_policy.md">bounty policy</a>.  
4. <b>File internal vulnerability tickets</b><br>
   * When issues are critical in nature, follow your <a href="https://www.sectemplates.com/2024/06/announcing-the-incident-response-program-pack-10.html">incident response process</a> to determine if an incident is required to address the issue immediately. <br>
   * Submit the vulnerability to the appropriate engineering or operations owner, notify them that the issue is incoming, and offer help to remediate the issue. <b>Never blindly file tickets to stakeholders that have been reported by an outside party.</b><br>
5. <b>Support engineering in developing a fix</b><br>
   * Engineering may want guidance on how to patch, mitigate, or fix the issue. This likely requires involving different subject matter experts within the security team, such as infrastructure/cloud security, product security, or secops. [1].   
6. <b>Confirm that the fix is correct by having a qualified representative of the security team perform the testing.</b><br>
   * If a qualified person exists, have them perform variations of the attack to attempt to bypass the fix. <br>
   * If no qualified person exists, reach out to the vulnerability researcher to assist with this process.<br>
7. <b>Notify the researcher of the deployed fix and ask them to test it</b><br>
   * Each company has a different process for release management, and some companies may choose to deploy each fix to staging or test environments before going live, while others will directly push to production. The culture of release management will influence how security fixes and mitigations are deployed. Once a fix has been deployed in a way that the external security researcher can test it, reach out and invite them to try and bypass your fix. They have expertise worth utilizing, are motivated to earn their bounty, and work collaboratively with you.
8. <b>Close issue as resolved</b><br>
   * Once the issue has been verified as fixed and that fix has been pushed to all of production, you can close the issue. Sometimes internal engineering or operations teams will want to close the issue once a fix is checked into the repository; however, that fix may not be deployed for some time. In the context of open security issues, they should remain open until verified to have gone live in production.
9. <b>Determine if issue requires public notification</b>
   * Determine if a public blog post, release note, email, or other notification should be sent or made available to customers. All external communication of a known security vulnerability should be reviewed by security leadership, engineering leadership, legal, and public relations. <br>
10. <b>Pay researcher</b><br>
    * At this stage, the researcher should be paid if they followed the policy outlined for your program and worked ethically with you.


## Appendix
[1] For externally reported issues, it's best to oversee each issue rather than assuming the vulnerability management process will handle it for you, at least in the beginning.

Runbook version 1.0 copied from [Sectemplates.com](https://www.sectemplates.com)
