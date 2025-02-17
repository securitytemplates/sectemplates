<b>Authors:</b> Incident Commander -  Morpheus (morpheus@therealworld.net) | Dan Kaminsky (dkaminsky@company.net) <br>
<b>Version:</b> 1.337<br>
<b>Created Date:</b> 5/7/24<br>
<b>Last Updated:</b> 5/9/24<br>
<b>Incident Level:</b> Sev 1<br> 
<b>Tickets:</b> e.g. [INCIDENT-31337](https://yourjira/INCIDENT-31337)<br> 
<b>Slack Channels:</b> #incident #incident31337 #engineering-escalation<br> 
<b>Working folder:</b> https://drive.google.com/?drive/folders/1c0VhaaSbnb4-RIsibf8DKdOlkHSsNn8m <br>
<b>Incident working document: </b>https://docs.google.com/?document/d/1WGz7WNNfoa9DhcOXpmLi0I_Mubc19VlqNSQ9SdHEEPc/edit<br>

# Summary of incident
On May 3rd 2024, our customer Acme called into support with an error trying to use the case management API. Support suspected a security issue, and reported that when escalating to Engineering. Engineering determined that there was a blind SQL injection (SQLi) vulnerability, and was able to push a fix to production at 2:48AM PST May 4th 2024. It was determined over the following days that NO unauthorized data disclosure occurred.

# Retrospective Participants
| Name     |  Role    | Involvement                  |
|----------|----------|------------------------------| 
|Johnny Mnemonic | Backend developer | Reported issue to Security| 
|Morpheus| Security Incident Commander | Project managed incident| 
|Grace Hopper| Director Infosec| Retrospective discussion|
|John Mcafee| Engineering Manager| Managed emergency fix |
|Dan Kaminsky| Basically Neo| Security oncall, performed forensic analysis| 
|Bob Knuth| Vulnerability management, Infosec| Retrospective discussion| 

# Meeting Notes
Incident document was reviewed by key incident stakeholders. Participants were asked to hold questions temporarily until that was complete, so that the questions could be recorded here.

Questions:
* Grace asked to confirm that we are confident that no data was accessed via this vulnerability. Dan confirmed that yes, he is very confident about that. We have log coverage, and exploitation had very clear indicators that would be present in these logs. Dan also notes that we were somewhat lucky with these logs, as this was not explicitly designed for.
* Morpheus asked if we COULD design for this kind of logging. This prompted a bit of a discussion about HTTP and SQL logging, performance impact, and so on. It was decided that the right people for that discussion were not in the room, and that John would drive the engineering investigation on that in conjunction with Product Security (ProdSec) and Incident Response (IR). 
* Bob points out that an outside party, Acme, might know about the security vulnerability, and asks if we will be publishing a security advisory on our advisories page. It was pointed out that we have not always published for internally-discovered vulnerabilities in the past, even if they had been live in production for a period of time before fix. The discussion determined that we WILL publish an advisory in this case, and generally plan to going forward for all vulns that end up in production for any period of time. There is potential reputational harm if it were found out that we would silently fix vulns.


# What went well? 
* Support recognized the potential security aspect, and escalated accordingly
* Vulnerability was remediated quickly, with no downtime
* Engineering team did an excellent job coming together quickly and getting the fix live
* No exploitation occurred
* Good logging was available (semi-accidentally), with good historic archiving

# What went ok?
* We were lucky that the problem generated a 500 error, and that the default 500 error logging contains enough detail for us to easily determine if it was related to this vuln
* This coming in late Friday is not ideal, but we note that we cannot plan when emergencies will happen

# What didn't go well?
<b>Note</b>: Every item that didn't go well should probably translate into an action item. 
* We have no proactive monitoring or alerting on this category of problem
* We don't currently have effective SAST coverage of this category of vulnerability for C code

# Action Items/Follow-ups
| Priority | Status| Action name | Action owner | Estimated resolution | Link to Jira ticket| 
|----------|-------|-----|--------------|----------------------|--------------------|
| P1 | Completed | Blind SQLi in case management API 2.0| John Mcafee|5/4/24| [PLAT-8675](https://yourjira/PLAT-8675)
| P1 | Planned | Sync with Legal, public relations, and engineering on external notification language| Morpheus| 5/30/24|
| P2 | Planned| Enhance SAST coverage, replace C API backend| John Mcafee | 9/30/24|[EPIC-309](https://yourjira/EPIC-309)
| P3 | Planned| Identify what logging and alerting enhancements can be made for these types of issues | Dan Kaminsky | 5/30/24| |

# Other Notes
* [Link to incident working document](https://docs.google.com/?document/d/1WGz7WNNfoa9DhcOXpmLi0I_Mubc19VlqNSQ9SdHEEPc/edit)
* Put other notes here that may prove useful in the future, but is currently unclear

Sample template version 1.5 copied from [Sectemplates.com](https://www.sectemplates.com) 2025
