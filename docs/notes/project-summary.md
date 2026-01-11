
# Project Documentation — Salesforce Agentforce (CC Service Agent)

## 1. Project Title
**Agentforce for Service — CC Service Agent (Coral Cloud Resorts)**

## 2. Objective
Coral Cloud Resorts experiences high seasonal demand, which increases customer support workload.  
The goal of this project was to configure an autonomous service agent using **Salesforce Agentforce** to:
- Answer customer questions about experiences/activities
- Validate customers securely
- Provide available sessions
- Create bookings in Salesforce
- Recommend personalized experiences

## 3. Solution Overview
A custom **Agentforce Service Agent** was created and deployed to an **Experience Cloud site** using **Embedded Messaging**.  
The agent uses:
- A custom topic (**Experience Management**) to define scope and guardrails
- Flow-based actions to retrieve and update Salesforce data
- A prompt-template action to generate personalized schedules

This enables customers to complete common booking tasks without requiring a human agent.

## 4. Components Built

### 4.1 Agent
- **Name:** CC Service Agent  
- **API Name:** CC_Service_Agent  
- **Type:** Agentforce Service Agent  
- **Status:** Active

### 4.2 Topic
A custom topic was created to handle the full guest journey around booking and managing resort experiences.

**Topic Name:** Experience Management  
**API Name:** Experience_Management  

**Key topic guardrails include:**
- Always validate customer identity before running other actions
- Ensure session dates are not in the past and normalize date format to `YYYY-MM-DD`
- Use Experience record IDs instead of names for session lookup
- Ask the guest to choose a session when multiple are returned
- Collect number of guests before booking creation

## 5. Actions Implemented
Five custom actions were attached to the topic to make the agent operational.

| Action Label | API Name | Type | Purpose |
|------------|----------|------|---------|
| Get Experience Details | Get_Experience_Details | Flow | Fetch details about a selected resort experience |
| Get Customer Details | Get_Customer_Details | Flow | Validate guest using email + membership number |
| Get Sessions | Get_Sessions | Flow | Retrieve available experience sessions by date |
| Generate Personalized Schedule | Generate_Personalized_Schedule | Prompt Template | Recommend experiences based on guest interests |
| Create Experience Session Booking | Create_Experience_Session_Booking | Flow | Create a booking record inside Salesforce |

## 6. Routing & Deployment

### 6.1 Omni-Channel Routing
The flow **Route to ESA** was updated to route messaging work to the new service agent:
- **Route To:** Agentforce Service Agent
- **Agent Selected:** CC Service Agent  
A new version of the flow was saved and activated.

### 6.2 Experience Cloud Deployment
The agent was embedded into the `coral-cloud` Experience Cloud site using:
- **Embedded Messaging component**
The site was published so customers can interact with the agent through chat.

## 7. Testing
The agent was tested using Conversation Preview and via customer view.

Example test prompts:
1. `Can you let me know about the Underground Cave Exploration?`
2. `I am sofiarodriguez@example.com and my membership number is 10008155`

Expected outcomes:
- Agent asks for guest identity if unknown
- Retrieves experience details
- Retrieves sessions
- Creates booking after guest selects session and provides number of guests

## 8. Key Skills Demonstrated
This project demonstrates hands-on skills in:
- Salesforce Agentforce Builder (Topics & Actions)
- Flow-based automation for agent actions
- Prompt Template integration for generative recommendations
- Omni-Channel routing configuration with flows
- Experience Cloud + Embedded Messaging deployment
- Trust and security concepts (identity validation, guardrails)

## 9. Screenshots / Evidence
Screenshots proving configuration and deployment are stored in:  
`docs/screenshots/`
