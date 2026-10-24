# n8n Lead Automation — The VIP Auto-Dialer

An automated lead qualification and sales outreach workflow built with n8n.

## About the Project

I built this project to explore how businesses can handle incoming leads without having to manually review every form submission, research each company, and decide who to contact first.

The idea was to create a workflow that could receive a lead, gather more information about the company, check whether the lead meets certain conditions, and automatically trigger the next action.

I used n8n to connect everything together, from the initial form submission to the notification and calling stages.

This is a personal project I built to practice workflow automation, API integrations, and conditional logic.

## How It Works

The workflow follows these steps:

1. **Lead Submission:** A potential customer submits their details through a Tally form. The submission triggers the n8n workflow through a webhook.

2. **Company Domain:** The workflow processes the submitted information to identify the company's domain.

3. **Company Enrichment:** An HTTP request retrieves additional company information from Apollo.io.

4. **Lead Qualification:** An IF node checks the enriched information against predefined conditions to determine which route the lead should follow.

5. **Qualified Leads:** Leads that meet the conditions trigger a Slack notification, followed by an HTTP request to Twilio's API for the calling step.

6. **Other Leads:** Leads that don't meet the conditions follow a separate route through Gmail.

The goal is to reduce the amount of manual work involved in moving a lead from form submission to the next sales action.

## Tools Used

| Tool | Purpose |
|---|---|
| n8n | Runs and connects the automation workflow |
| Tally | Collects incoming lead information |
| Apollo.io | Provides additional company information |
| Slack | Sends notifications for qualified leads |
| Twilio | Handles the calling API integration |
| Gmail | Handles the alternative email route |

The workflow also uses webhooks, HTTP requests, and conditional logic to connect these services.

## Workflow Overview

Tally Form → Company Domain → Apollo.io → Lead Qualification

From there:

- **Qualified:** Slack Notification → Twilio API Request
- **Not Qualified:** Gmail Email Route

## What I Learned

Building this workflow gave me more hands-on experience with:

- Connecting different applications through APIs and webhooks.
- Working with HTTP requests and API responses.
- Processing incoming form data.
- Using conditional logic to route data through different parts of a workflow.
- Understanding how automation can support sales and lead management processes.

One of the most interesting parts was getting different services to work together as one process instead of treating them as separate tools.

## Running the Workflow

If you'd like to explore the workflow yourself:

1. Download the JSON workflow file from this repository.
2. Open your n8n instance.
3. Import the workflow JSON.
4. Set up your own credentials for the required services.
5. Configure the Tally webhook, Apollo.io API request, Slack, Gmail, and Twilio integrations.
6. Review the qualification conditions and update them for your use case.
7. Run a test submission to verify the workflow before activating it.

You'll need accounts and the appropriate API access for the services you want to use.

The exported workflow is a reference implementation, so some configuration will be required before it can run in another environment.

## Project Status

This is a self-initiated project built for learning and demonstration purposes, not a production deployment for a client.

I plan to keep improving my automation skills and explore more ways to build useful workflows for real business processes.

## Let's Connect

I'm interested in backend development, API integrations, and building automation systems that solve practical business problems.

If you're working on something similar or would like to collaborate, feel free to connect with me on [LinkedIn](https://www.linkedin.com/in/abdullahijumah/).
