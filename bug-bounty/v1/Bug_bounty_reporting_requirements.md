# Bug Bounty Reporting Requirements

## About
This document outlines the basic information you'll need from a security researcher or vulnerability reporter as part of a bug bounty program.

## Description of Issue
The vulnerability report should provide information on what the security researcher believes is the worst thing that can happen. This will serve as a starting point for internal investigations but may not represent the entirety of the impact. Often, the researcher will only discover a portion of the impact of the issue they found. They may not be aware of the issue in the context of other workflows, account states, or edge cases that could make their issue much worse than they believed.

<b>Note:</b> Never assume the security researcher’s report fully describes the scope of the issue. 

## Reproduction Instructions
It's essential to get detailed reproduction instructions from the security researcher. They may provide minimal information, making reproduction difficult, sometimes due to certain preconditions not being met. Examples of preconditions include:
  * A certain user role must be used, for example, 'manager'.
  * A specific session state needs to be established. For example, if there is a multi-page workflow, it may require going through the first two pages to exploit the issue on the third page. Hitting the third page without meeting these preconditions may result in the issue not being exploitable.
  * A verified account. For example, the user may have to pass a KYC workflow or perform a certain action on the platform that gives their account 'status'. This may be required to hit the endpoint with the right state to exploit it.
  * Account age may also play a role if age is tied to unlocking particular functionality.<br><br>
<b>Important note:</b> If you receive a file or video from a security researcher, you must assume it is hostile. You will need a secure environment (e.g., a disposable virtual machine) to view these files, as they could be an attempt to compromise your company. Never assume a file is safe to handle. <br>

## Accounts Used as Part of Testing
Some security researchers will get nervous if you ask them for the name of the account they used for testing. It's a good idea to ask them and to set the tone that you're just interested in understanding the full scope of their testing to determine if something they did triggered a specific precondition to be met. It's not advised to push the researcher too hard, as they may become uncooperative or unresponsive.

Document version 1.0 copied from [Sectemplates.com](https://www.sectemplates.com)
