<b>Authors:</b> Incident Commander -  Morpheus (morpheus@therealworld.net) | Dan Kaminsky (dkaminsky@company.net) <br>
<b>Version:</b> 1.337 <br>
<b>Created Date:</b> 5/3/24 <br>
<b>Last Updated:</b> 5/7/24 <br> 
<b>Incident Level:</b> Sev3 (medium)<br> 
<b>Tickets:</b> [INCIDENT-31337](https://yourjira/INCIDENT-31337) <br> 
<b>Slack Channels:</b> #incident #incident31337 #ops <br> 
<b>Working folder:</b> https://drive.google.com/drive/folders/1c0VhaaSbnb4-RIsibf8DKdOlkHSsNn8m <br> 

# Title: SQLi reachable via REST API

# Summary of incident
Customer Acme reported to Support that they receive an error when using the case management API. Support determined through experimentation that the error occured when an apostrophe was used in the name field. The case was referred to Engineering to fix, and the engineer determined that there was a potentially exploitable SQL injection vulnerability. A code fix has been developed, tested, and pushed to production. 

# Detailed description
Acme called Support to get help using the case management feature API. They noted that the same query via the web UI works fine, but fails on the REST API. Justyn Tyme from support was working with the customer, and noted that the API call failed only when the name field was "O'Malley". Names without ' worked just fine. Justyn created a support ticket [SUPPORT-65535](https://yourjira/SUPPORT-65535), which was later cloned to [PLAT-8675](https://yourjira/PLAT-8675) to support engineering. <br><br>
Justyn noted the problem with the customer, and told them he had filed a medium severity support ticket, so the customer could expect the next response to be as long as two business days per support contract SLA. However, Justyn was suspicious about the apostrophe, so referred the platform ticket to the on-call L2 support escalation from Engineering (Johnny Mnemonic) in the #support-escalation channel, where he called out the issue as potentially having security implications.  It turned out to be fortunate that Johnny was the one on escalation on-call, as he was very familiar with the functionality and code base for this backend functionality. Johnny was able to quickly replicate the issue in the testing environment, and looking at the code, believed there was in fact SQLi reachable via the REST API. He was able to update a row in the case table (test environment) via blind SQLi. <br><br>
Johnny posted a message in #incident indicating a live vulnerability in production has been discovered, and that it needed to be investigated. Morpheus responded with "on it", and DM'd Johnny for details. Johnny pointed him at PLAT-8675, and filled him in on verification details that he had not yet added to the ticket.<br>
Morpheus created ticket INCIDENT-31337 to collect details and progress, and private channel #incident31337 for discussion and coordination. He initially invited Johnny, Johnny's manager John Mcafee from Engineering, and team member Dan Kaminsky. In this channel for initial triage, the following items were discussed: <br>
* Johnny Mnemonic provided curl examples for how to reproduce the problem, and the sample "exploit" tested
* Johnny provided a link to the git repo showing the vulnerable code, which was old C code using direct SQL DB access with a crafted query string, rather than using a parameterized SQL query
* Johnny also provided commentary and links to the web UI version of the code performing equivalent functionality, which was Python code, and did not use the vulnerable API to implement it
* Morpheus requested information about when the code was introduced (git showed 2/2/21), and when it went into production
* John Mcafee took action item to have his team determine when the vulnerability went live in production
* Dan asked if there was any way to determine if this vulnerability had ever been used, it's speculated that maybe HTTP 500 errors (which occur when it's used) on that URL may be searchable
* Johnny implements a fix (fix is to convert to parameterized query) relatively quickly. , John gathers other team members off-channel for code review, QA, and push to test
* Dan takes action to research logs or other forensic data to attempt to determine any past exploitation <br>
<br>
Emergency fix was pushed to production at 2:48AM PST. Support was notified via email to watch out for problems related to the change, and given 'the ok' to contact Acme to retest their issue. Vulnerability is believed to be remediated for now, engineering agrees to reconvene during business hours on Monday, so that everyone can get some sleep. Security's priority at this point, is to determine if there has been any active exploitation.<br><br>

Further details are shared in the private incident channel over the weekend. It turns out Dan worked over the weekend, and was able to determine that the exploit has not actively exploited. We retain all old HTTP server logs in long-term storage, which Dan was able to check for combinations of 500 errors against that API URL. The 500 errors also log a call trace and parameter dump, allowing him to inspect roughly what was passed, and compare those against successful exploitation in the test environment logs. Dan found a total of 104 500 errors against that endpoint, first one being 6/16/21. All of which appear to be accidental triggers rather than any attempt at deliberate probing or exploitation. Dan also notes that the first usage of that API endpoint at all appears to be 3/10/21, which seems to correspond well with the 2.0 API go-live on 3/1/21.<br><br>
Engineering is tracking EPIC-309 for the big-picture efforts to remediate this vulnerability. Please see that epic for details, but current plans include:<br>
* Manually check C code for any remaining SQL queries with similar problems
* Craft SAST rule to detect problematic SQL queries in C code (we already have coverage for Python)
* Long-term plan to convert (now-exposed) legacy API code to current Python standard
* Long-term plan to rearchitect backend so there is a single API point for REST and web UI usage
* Evaluate what additional logging can be added within performance constraints, such as SQL query logging, or ability to alert for strange SQL queries
* Evaluate switching to SQL parameterized queries only<br>
<br>
At this point, the active incident is concluded. Engineering has a working fix in production and plans for improvement. Security has the vulnerability remediated, and is satisfied that it was not utilized and no sensitive data was accessed. Remaining steps will take place as part of the retrospective effort, including notification to management (that thankfully includes that no customer data was accessed inappropriately), and decisions about vulnerability fix notification.

# Action Items/Followups
| Priority | Status| Action name | Action owner | Estimated resolution | Link to Jira ticket| 
|----------|-------|-----|--------------|----------------------|--------------------|
| P1 | Completed | File behavior as a defect within appropriate engineering team| John Mcafee|4/20/24| [EPIC-309](https://yourjira/EPIC-309)  
| P1 | Planned| Schedule incident retrospective| Morpheus | 4/22/24| [INCIDENT-31338](https://yourjira/INCIDENT-31338)|

# Stakeholders
| Name     |  Role    | Involvement                  |
|----------|----------|------------------------------| 
|Justyn Thyme | Senior support engineer | Reported issue| 
|Johnny Mnemonic | Backend developer | Triaged issue| 
|Morpheus| Security Incident Commander | Project managed incident| 
|John Mcafee   | Engineering Manager| Mobile, Eng team |
|Dan Kaminsky| Basically Neo| Security oncall that performed all forensic and technical analysis.| 
# Incident timeline
Date - Time + Timezone + Description of event<br> 
2/2/21 - Vulnerability introduced into codebase <br> 
3/1/21 - Vulnerable code is deployed to live production<br> 
5/3/24 - 11:20AM PDT - Customer notices issue and calls support<br>
5/3/24 - 12:08PM PDT - Support notifies Engineering<br>
5/3/24 - 01:32PM PDT - Engineering notifies Security<br>
5/3/24 - 01:47PM PDT - Incident channel is created<br>
5/4/24 - 02:48AM PDT - Fix pushed to prod<br>
5/4/24 - 05:11PM PDT - Dan posts to channel that vuln was not exploited<br>
5/6/24 - 10:05AM PDT - Channel votes that emergency portion of incident is concluded<br>


# Incident materials
[Google drive folder URL](https://drive.google.com/drive/folders/1c0VhaaSbnb4-RIsibf8DKdOlkHSsNn8m<br>)
# Other References
* Link to incident raw notes or working folder

Sample template version 1.5 copied from [Sectemplates.com](https://www.sectemplates.com) 2025
