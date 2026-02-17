🚀 AI Resume Filter Agent
(n8n + Groq LLM Automation)

An AI-powered resume evaluation system built using n8n workflow automation and Groq LLM (gpt-oss-20b).

This system automatically evaluates candidate resumes against a job description, generates a structured AI assessment, and stores results in Google Sheets.

🔥 Key Features

📥 Accepts resume data via Webhook (POST API)

🧠 AI-powered evaluation using Groq LLM

🎯 Skill matching & gap analysis

📊 Automated scoring (0–100)

🏷 Fit level classification (High / Medium / Low)

📄 Structured JSON output enforcement

📈 Automatic storage in Google Sheets

⚡ Fully automated backend workflow

🧠 Tech Stack
Technology	Purpose
n8n (Self-Hosted)	Workflow automation engine
Groq LLM (openai/gpt-oss-20b)	Resume evaluation & scoring
Google Sheets API	Data storage
Postman	API testing
ngrok	Secure local webhook tunneling
🏗 System Architecture
Webhook → AI Agent → Data Parsing → Google Sheets

Flow Explanation:

Webhook receives resume data via POST request

AI Agent (Groq LLM) evaluates candidate using structured prompt

Output is parsed into strict JSON format

Results are manually mapped into Google Sheets

📥 API Usage
Endpoint
POST /webhook-test/upload_resume

Sample Request Body
{
  "name": "John Doe",
  "email": "john@example.com",
  "resume_text": "I am a React developer with 2 years of experience...",
  "job_description": "Looking for a React developer with Node.js experience."
}

📊 AI Output Format

The system enforces strict structured output:

{
  "name": "string",
  "email": "string",
  "score": number,
  "fit_level": "High/Medium/Low",
  "strengths": "comma separated string",
  "weaknesses": "comma separated string"
}

⚙ Engineering Decisions & Implementation Notes

Initially attempted PDF parsing using n8n Python node

Faced Python runner limitation in internal mode

Redesigned architecture to accept structured JSON input

Implemented strict JSON enforcement in LLM prompt

Debugged webhook body structure ($json.body.*)

Used ngrok to expose local n8n instance securely


💡 What This Project Demonstrates

✅ AI Agent orchestration

✅ Prompt engineering with structured output control

✅ Workflow automation architecture

✅ API testing & webhook handling

✅ LLM debugging & output validation

✅ Cloud tool integration

✅ Practical production-style troubleshooting

📷 Workflow Architecture

See:

/screenshots/workflow-architecture.png

🎯 Project Impact

This project simulates a real-world HR automation pipeline, demonstrating how AI agents can be integrated into workflow automation systems for scalable candidate evaluation.
