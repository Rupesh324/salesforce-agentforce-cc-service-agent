# Setup Steps — CC Service Agent

## 1. Enable Einstein + Agentforce
- Setup → Einstein Setup → Turn ON
- Setup → Salesforce Go → Agentforce (Default) → Turn On

## 2. Create agent
- Setup → Agentforce Agents → New Agent
- Type: Agentforce Service Agent
- Name: CC Service Agent
- API Name: CC_Service_Agent
- Agent User: EinsteinServiceAgent User
- Enable enhanced event logs
- Activate agent

## 3. Create custom topic
Topic:
- Name: Experience Management
- API: Experience_Management

Includes 6 instructions for:
- customer verification
- date conversion
- session retrieval
- booking creation
- recommendations

## 4. Create actions
Actions created and attached to topic:
- Get Experience Details (Flow)
- Get Customer Details (Flow)
- Get Sessions (Flow)
- Generate Personalized Schedule (Prompt Template)
- Create Experience Session Booking (Flow)

## 5. Route flow
Flow: Route to ESA
- Route To: Agentforce Service Agent
- Agent: CC Service Agent
- Save as new version + activate

## 6. Deploy to Experience Cloud
- All Sites → coral-cloud → Builder
- Add Embedded Messaging component
- Publish site

