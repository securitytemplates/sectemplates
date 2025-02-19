# Bug Bounty Metrics

## About
This document outlines good starting metrics to measure the effectiveness and operations of your bug bounty program.

## Total Bounties Paid Out
This can contain several views 
  * <b>Month over month payouts:</b> Indicate volume and critical trends.
  * <b>Quarterly payouts:</b> Quarterly snapshots can be useful for quarterly business reviews (QBRs) with executives.
  * <b>Payout by severity:</b> This can measure where money is being spent and can be used to modify the payout amounts, scope or focus for researchers, or signal the need for automation investments.


## Time to Respond to Report
From the time the issue is filed to the bounty program, how long did it take for the security team to get looped in? This can be utilized in two ways:
  * When a bug bounty service performs an initial review, you can measure how long they take to evaluate the issue. This measures the operational effectiveness of your bug bounty provider. Some providers have this metric in their dashboards.
  * When a bug bounty service is paid to perform an initial analysis, verifies the issue is real, and sends it to your team, how long does it take for your team to respond? This measures operational effectiveness within your company.

## False Positive vs Out of Scope Submissions
Of the number of issues submitted, what percentage were real? This can be further broken down into:
  * <b>Number of issues submitted out of scope:</b> This can determine if people either aren't reading the rules of engagement in your <a href="./Bug_bounty_simplified_policy.md">bounty policy</a>, or if it needs to be updated to provide further clarification.
  * <b>Number of false positives eliminated by bounty service triage:</b> When you're paying a bug bounty provider to perform initial analysis, you can measure how many issues and how much time they have saved your team. You can then determine if any additional triage costs are worth it, or if it's worth performing this internally to save money. 

## Vulnerability Types
By charting and measuring specific vulnerability classifications, you gain signals on quality problems in your products or security controls that may be lacking. For example:
  * Poor output filtering frameworks which result in <a href="https://www.cgisecurity.com/xss-faq.html">cross-site scripting</a>.
  * IDOR/authorization issues due to lack of a standardized auth framework.
  * Poor error handling resulting in stack traces and sensitive information being disclosed.
This information can then be provided to your product security and engineering teams to tackle common issues strategically and proactively.

Metrics version 1.0 copied from [Sectemplates.com](https://www.sectemplates.com)

## Volume based on severity
This helps determine the severity of submissions you are getting. As you mature your program, you can try different things to try and increase the P0/P1 submissions.
