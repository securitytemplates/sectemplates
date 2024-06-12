# Incident response preparation checklist

## About
This document outlines the preperation, activities, and considerations required to stand up a minimal security incident response program. 

## IR program preparation checklist
This section outlines initial activities and considerations to hash out to build your initial IR program. 
- [ ] <b>Determine incident response program owner:</b> An owner for the security incident response process needs to be identified, most often this person resides within the security team but this isn't required. 
- [ ] <b>Determine incident response support periods:</b> In smaller organizations 24/7 coverage is unlikely, and there may only be someone available initially during business hours. It's important to understand who is available to assist with incidents, and what happens when they are sick or unavailable. 
- [ ] <b>Determine incident response support staff:</b> Ideally, you have at minimium 2 individuals that can be pinged for security oncall, with an agreement on after hours support for each member. If you're utilizing a solution such as pagerduty, ensure these individuals are properly registered.
- [ ] <b>Establish incident response public channel for centralized communication:</b> Creating a public #incident channel is a good idea. You will need to negotiate with your SRE/engineering teams to determine if the main #incident channel should be used for both security and non security incidents, or if another dedicated public channel should be created. Regardless of the decision, the responsible parties for the main #incident channel need to know when and how to redirect security related incidents to the right channel. 
- [ ] <b>Develop an incident response runbook:</b> Security incident responders should have a playbook, or runbook to enable them to consistently investigate and drive incidents. A <a href="./Incident_response_runbook.md">sample incident response runbook is available</a> within this release pack. 
- [ ] <b>Develop an incident response working document template:</b> Each incident should have an associated document that captures everything involved. A <a href="./samples/">sample incident response working document is available</A> within this release pack.
- [ ] <b>Determine ticketing used to track incidents:</b> Each incident should have an associated ticket in your bugtracker, such as Jira. It's safer to lock down incident tickets to only those involved as it may contain PII, employee information, or information that could compromise the security of the company.
- [ ] <b>Determine postmortem template:</b> Minimally, each high or critical incident should have a postmortem to evaluate how the incident operated, to discuss root causes, and to determine followup items. A <a href="./samples/">blameless postmortem document template is available</a> within this release pack. 
- [ ] <b>Run test incident to verify process:</b> It's important to know that when something occurs, your process is functioning and the initial issues have been worked out. It's strongly recommended you perform a practice run, using a tabletop exercise to simulate a breach and how you and your stakeholders would respond to it. 
- [ ] <b>Develop inventory of stakeholder point of contacts (POCs):</b> During an incident it's critical to reach the right technical stakeholders, and owners who can help with analysis, and decision making. It's recommended you develop a sample point of contact spreadsheet that's always updated<br>

    | Name     |  Role    | Team channel                  | Emergency contact info|
    |----------|----------|------------------------------|------------------------| 
    |Johnny Mnemonic | Mobile app developer | #mobile-eng| See workday
    |Ralfi Face | Mobile app manager | #mobile-eng | 555-867-9309
    |SRE Oncall| Main SRE oncall alias| #sre-eng| Tag @SRE-Oncall in main channel|

- [ ] <b>Optional Incident response retainer:</b> There are companies that offer on demand incident response support that you can pull in as needed. This will likely cost between 30k-100k USD and will ultimately be determined based on your budget. 

## After completing the checklist
Please see the <a href="./Incident_response_runbook.md">incident response runbook</a> for information on handling an incident. 

Checklist version 1.0 copied from [Sectemplates.com](https://www.sectemplates.com)
