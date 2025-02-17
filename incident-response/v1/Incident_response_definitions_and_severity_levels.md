# Definitions and terminology
This document outlines terminology used throughout the incident response materials, as well as defines incident severity levels to enable consistent operations.<br>

# Incident Commander
<b>Definition</b>: The Incident Commander role is the primary point of contact for a security incident, and may or may not be the manager of the security incident response team. There may be multiple incident commanders during an incident depending on the incident duration, work shift overlaps, and timezones involved; however only one person should own the overall incident from the security side. Each incident should have one commander primarily responsible for the actions below.<br>

<b>Responsibilities</b>:<br>
* Primary point of contact for a security incident for all stakeholders.
* Ensures the right stakeholders are found and looped in.
* Ensures that key points are captured in the <a href="./Security_incident_working_document_template.md">incident working document</a>, significant events are captured in the timeline, action items and owners are identified, incident priority is verified/determined if it should be increased/decreased, and to formally call a close to the incident. 
* Responsible for executive communication preparation (when applicable).
* Panic management: During an incident things may become heated as a result of the 'fog of war' during a security incident. The incident commander shall take necessary steps to ensure stakeholders remain calm and focused. This may include removing people who are providing no value to the investigation. 
* Scheduling blameless retrospectives, also known as postmortems, with key stakeholders involved in the incident. This will enable all stakeholders to weigh in on how the incident was handled, and to review the follow-up action items and hand off. 
* Delegator of tasks to subject matter experts.
* Ensures the incident ticket is filed according to internal processes. 

<b>Note</b>: If possible, finding a project manager to assist with coordination of tasks, open questions requiring answers, and follow-up items. This will enable the incident commander to focus on driving the incident efficiently. 

# Security Analyst/Engineer/Security Oncall
<b>Definition</b>: A member of the security team looped in to perform technical analysis of the incident. 

<b>Responsibilities:</b><br>
* Technical analysis of the incident. Typically involving system expertise, product expertise, monitoring expertise, and forensic expertise. 
* Remediation research, and guidance for confirmed vulnerabilities or threats.
* Remediation development in combination with engineering/ops key subject matter experts. 
* Captures key events in the incident working document.
* Pulls in incident commander when necessary.

# Incident supporter
<b>Definition</b>: A representative from engineering (most often a software engineer), site reliability engineer, or product manager which provides subject matter expertise and support during, and after an incident.

<b>Responsibilities:</b><br>
* Assists with root cause identification, impact analysis, remediation efforts, action item ownership or identification, and general subject matter expertise involved with the applications/systems involved.

# Key non security incident stakeholders
The following list outlines common stakeholders that will be involved with a security incident or breach. 
* <b>Product manager:</b> Owner of the product or service impacted by the incident.
* <b>IT engineers and management:</b> Front line engineers helping to troubleshoot, and resolve the incident. 
* <b>Site reliability engineer:</b> Front line engineers helping to troubleshoot, and resolve the incident. 
* <b>Software engineer:</b> Front line engineers helping to troubleshoot, and resolve the incident. 
* <b>Engineering manager:</b> Front line leadership helping to troubleshoot, and resolve the incident. 
* <b>Engineering director:</b> Escalation path when an incident becomes considerable, or verified to be of concern. 
* <b>Public relations:</b> If the need arises to make a public statement on the incident, public relations should be looped in to vet the wording in combination with the legal and security team. 
* <b>Legal team:</b> If a breach or data leakage is suspected, your company's legal team should be notified immediately.  
* <b>Executive leadership team:</b> Final escalation path for critical incidents where legal, and security leadership at minimal believe notification or decisions are required from above. 
* <b>Human Resources:</b> When an employee is participating in malicious behavior HR will need to be notified by the incident commander. 


# Incident response levels
It is strongly encouraged that you insert these security incident response levels into your existing incident response process vs having a second stand alone document. This provides a centralized view for different categories of incidents, with clear criteria to help non-security stakeholders determine whether an incident is security related. <br>

We also recommend customization of the table below, that align closely with your business objectives and risk concerns (e.g. data exposure, money loss, physical security concerns, etc..).  

| Severity| Criteria description | Impacts| Notifications required|Examples|
|---------|----------------------|-------|------------------------|---------|
|Sev1 (Critical)| Critical impact to users, company systems, partner systems, or company reputation. | Large number of users, or critical production systems impacted| Security team leadership + Eng leaders + Executive updates | A customer-facing service is down for all customers, or sensitive data access by an unauthorized person/system.|
|Sev2 (High)| High impact to users, company systems, or partner systems. | Limited number of users impacted, important production systems impacted| Security team oncall | A customer-facing service is down for a subset of customers| 
|Sev3 (Medium)| Moderate impact to users, company systems, or partner systems. | Small number of users impacted| Security team oncall | Minor inconvenience for customers, but still usable|
|Sev4 (Low) | Minimal impact to users, or systems. Little or no risk to organization assets or reputation.| No direct user or service performance impact |Security team oncall | No impact to customers|


Document version 1.5 copied from [Sectemplates.com](https://www.sectemplates.com) 2025
