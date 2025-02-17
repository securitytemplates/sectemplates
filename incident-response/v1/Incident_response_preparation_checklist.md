# Incident Response Program Preparation Checklist

## About
This document outlines the preparation, activities, and considerations required to establish a minimal <a href="https://www.sectemplates.com/incident-response/">security incident response program</a>. 

## IR program preparation checklist
This section outlines initial activities and considerations to develop your initial IR program. 
- [ ] <b>Determine Incident Response Program Owner:</b> An owner for the security incident response process needs to be identified, most often this person resides within the security team but this isn't required. 
- [ ] <b>Determine Incident Response Support Periods:</b> In smaller organizations 24/7 coverage is unlikely, and there may only be someone available initially during business hours. It's important to understand who is available to assist with incidents, and what happens when they are sick or unavailable. 
- [ ] <b>Determine Incident Response Support Staff:</b> Ideally, you have at minimum 2 individuals that can be pinged for security oncall, with an agreement on after hours support for each member. If you're utilizing a solution such as PagerDuty, ensure these individuals are properly registered.
- [ ] <b>Establish Incident Response Public Channel for Centralized Communication:</b> Creating a public #incident channel is a good idea. You will need to negotiate with your SRE/engineering teams to determine if the main #incident channel should be used for both security and non security incidents, or if another dedicated public channel should be created. Regardless of the decision, the responsible parties for the main #incident channel need to know when and how to redirect security related incidents to the right channel. 
- [ ] <b>Develop an Incident Response Runbook:</b> Security incident responders should have a playbook, or runbook to enable them to consistently investigate and drive incidents. A <a href="./Incident_response_runbook.md">sample incident response runbook is available</a> within this release pack. 
- [ ] <b>Develop an Incident Response Working Document Template:</b> Each incident should have an associated document that captures everything involved. A <a href="./samples/">sample incident response working document is available</A> within this release pack.
- [ ] <b>Determine Ticketing System Used to Track Incidents:</b> Each incident should have an associated ticket in your bugtracker, such as Jira. It's safer to lock down incident tickets to only those involved as it may contain PII, employee information, or information that could compromise the security of the company.
- [ ] <b>Determine Postmortem Template:</b> Minimally, each high or critical incident should have a postmortem to evaluate how the incident operated, to discuss root causes, and to determine follow-up items. A <a href="./Security_incident_blameless_postmortem_template.md">blameless postmortem document template is available</a> within this release pack. 
- [ ] <b>Run Test Incident/Tabletop to Verify Process:</b> It's important to know that when something occurs, your process is functioning and the initial issues have been worked out. It's strongly recommended you perform a practice run, using a tabletop exercise to simulate a breach and how you and your stakeholders would respond to it. 
- [ ] <b>Develop an Inventory of Stakeholder Points of Contacts (POCs):</b> During an incident it's critical to reach the right technical stakeholders, and owners who can help with analysis, and decision making. It's recommended you develop a sample point of contact spreadsheet that's always updated with key stakeholders from Legal, HR, Marketing, SRE, Operations, Engineering, etc... As part of this process, it's essential to reach out to each stakeholder to discuss expectations, and possible support needed from them or their teams. <br>

    | Name     |  Role    | Team channel                  | Emergency contact info|
    |----------|----------|------------------------------|------------------------| 
    |Johnny Mnemonic | Mobile app developer | #mobile-eng| See workday
    |Ralfi Face | Mobile app manager | #mobile-eng | 555-867-9309
    |SRE Oncall| Main SRE oncall alias| #sre-eng| Tag @SRE-Oncall in main channel|
- [ ] <b>Establish law enforcement communication channels:</b> When an incident occurs that requires law enforcement, you don't want to have to figure out how to establish the relationship in that moment. It's recommended that you establish points of contact for your local law enforcement office (e.g. local FBI field office) in collaboration with your legal team. This enables you to understand how, and when to loop them in collaboration with your legal team.
- [ ] <b>Determine Legal SLA Notification Requirements</b>: There may be contractual or legal requirements to notify customers of security incidents within a specific timeframe. It is essential to determine the legal deadlines for public statements and ensure they are incorporated into your runbooks and processes.
- [ ] <b>Optional Incident Response Retainer:</b> There are companies that offer on demand incident response support that you can pull in as needed. This will likely cost between 30k-100k USD and will ultimately be determined based on your budget.

## After Completing the Checklist
Please see the <a href="./Incident_response_runbook.md">incident response runbook</a> for information on handling an incident. 

## Additional resources
- [ ] <b>Incident Response Automation:</b> Netflix has an open source tool called <a href="https://netflixtechblog.com/introducing-dispatch-da4b8a2a8072">Dispatch</a> that can help automate the aspects of responding to an incident. 


Checklist version 1.5 copied from [Sectemplates.com](https://www.sectemplates.com) 2025
