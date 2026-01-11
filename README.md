

# Salesforce Agentforce Project — CC Service Agent

## Project Summary
This project demonstrates how to configure and deploy an autonomous customer support agent using **Salesforce Agentforce for Service**.

The agent assists Coral Cloud Resorts customers by:
- Providing information about resort activities and experiences
- Validating customer identity (email + membership number)
- Fetching available sessions
- Creating bookings in Salesforce
- Generating personalized schedule recommendations

---

## Tools & Features Used
- Agentforce Builder (Service Agent)
- Custom Topic: **Experience Management**
- Actions built with:
  - Salesforce Flows
  - Prompt Template (Prompt Builder)
- Omni-Channel Routing Flow: **Route to ESA**
- Experience Cloud deployment with **Embedded Messaging**
- Einstein Trust Layer concepts (security, guardrails, safe grounding)

---

## Architecture
Customer (Experience Cloud Embedded Messaging)
→ ESA Web Deployment
→ Omni-Channel Flow (Route to ESA)
→ Agentforce Agent (CC Service Agent)
→ Actions (Flows + Prompt Template)

---

## Actions Implemented
| Action Label | API Name | Type |
|------------|----------|------|
| Get Experience Details | Get_Experience_Details | Flow |
| Get Customer Details | Get_Customer_Details | Flow |
| Get Sessions | Get_Sessions | Flow |
| Generate Personalized Schedule | Generate_Personalized_Schedule | Prompt Template |
| Create Booking | Create_Experience_Session_Booking | Flow |

---

## Example Test Prompts
1. `Can you let me know about the Underground Cave Exploration?`
2. `my email is sofiarodriguez@example.com and my membership number is 10008155`

---

## Screenshots / Evidence
All screenshots are in `docs/screenshots`.

- Agent created and activated (CC Service Agent)
- Experience Management topic with instructions
- 5 custom actions added (Flows + Prompt Template)
- Flow routing updated (Route to ESA → CC Service Agent)
- Embedded Messaging deployed on Experience Cloud site
