Project 2 — WhatsApp Airtable Agent (n8n + AI)
This project is an advanced automation workflow built in n8n that integrates WhatsApp, Airtable, and OpenAI. It is designed to manage initial user interactions by ensuring data integrity through a "Source of Truth" database before generating intelligent, AI-powered responses.

Candidate
Enzo Lopes

Workflow designed to optimize data ingestion and lead management
Currently pursuing a postgraduate degree in Data Science and Analytics at PUC-Rio


Naming Conventions

Trigger → The incoming WhatsApp message via Webhook
Node → Each individual step (Parsing, Search, Insert, IA) inside the workflow
Source of Truth → The Airtable cloud database that holds the master record of all users


Workflow Functions
1. Data Normalization & Cleaning
The process begins by receiving raw data from a Webhook. The workflow immediately executes:

Parsing: Converting raw input into a structured format.
Normalization: Treating strings and JSON data to ensure consistency across the database.

2. Database Verification (Search/Insert Logic)
Before any interaction, the workflow prioritizes data integrity:

Search: It queries the Airtable cloud database to check if the user is already registered.
Conditional Logic: If the user is new, an Insert node automatically creates a unique record. This prevents database noise and duplicate entries.

3. Flow Cadence & UX
To ensure a natural user experience:

Wait Node: The workflow implements a timed delay to allow backend processes (Database and IA) to finish.
Feedback: The system can provide immediate registration confirmation to the user.

4. AI-Contextualized Response
Only after the data is verified and registered does the intelligence layer act:

OpenAI (GPT-4o-mini): Generates a personalized response based on the message content.
Sender WPP: The final response is dispatched back to the user via the WhatsApp API.


Goal
To build a scalable and robust "Data-First" automation that eliminates repetitive manual registration and leverages AI to provide immediate, high-quality customer service.
