# Agent Instructions

These instructions need to be done in order.

## Set 1: Retrieve Communication Data
1. [GMAIL Plugin] Iterate though all email communication with <DOMAIN_NAME> and extract the following information:
2. Generate a json file named <domain>-timeline.json containing a timeline of communication with the recipient domain, and the contacts we emailed.
eg.
```json
{
    "domain": "trivalleyhealth.com" ,
    "contacts": ["info@trivalleyhealth.com"],
    "timeline": [
        "Jan 10, 2025 - Initial outreach requesting registration. No response",
        "Sept 1, 2026 - Follow up email. No response"
    ]
}
```
contacts should be a list of email addresses sent to that domain across all communication (not just the initial outreach). If multiple unrelated recipient domains are found, on the same email (such as BCC), ignore them.

3. Timeline should be single line summaries of the sent email communication (or responses) from the provider. If a response is received, create a new line, otherwise append "no response" on the same line. Ignore automated responses from Vacation responders. Ignore automated response if delivery failed. Keep line factual and terse.

"Jun 9, 2026 - Initial request, no response"
"July 20, 2026 - follow up, NIH response that “Any expansion of government software is through the official contract award process.”"
"July 21, 2026 - fasten added clarification that we’re requesting access to their EHR on behalf of Patients, not trying to sell them software. No response"

4. Generate a PDF of the email threads for a specific domain, named <domain>-communication.pdf. Provide this in addition to the JSON file

## Set 2: Populate Information Blocking Complaint Template
1. parse <domain>-timeline.json
2. Populate the following template. Using the following variables and data from <domain>-timeline.json
- ORGANIZATION_NAME: 
- URL:
- EHR:
        
```      
I am the CEO of Fasten Health, Inc. a Personal Health Record (PHR) application that allows patients to generate a longitudinal health record using Patient Access APIs.

I’m submitting an Information Blocking Complaint against:

- **Name:** {"Organization Name" from variables}
- **Website:** {"URL" from variables}
- **Role:** Health Care Provider
- **Purpose of request:** Application Registration with Certified IT EHR
- **EHR:** {"EHR" from variables}

Contacts:

- {List of "contacts" from JSON file entry}

I have attempted to register Fasten Health with {"Organization Name" from variables}’s {"EHR" from variables} Patient Access FHIR API so that individual {"Organization Name" from variables} patients can authorize Fasten to retrieve their own health information. The {"Organization Name" from variables} has not registered our application.

Timeline:
- {List of "timeline" from JSON file entry}

I’ve attached a PDF of our email thread
```

3. This file should be named  "{"domain" from JSON file entry}.complaint.md"
4. Once complete all generated files should be zipped up and made available to me 
5. For any entry that was not found in meditech-organizations.csv, add the "domain" to a list in missing.txt and provide that file in addition to the zip file
