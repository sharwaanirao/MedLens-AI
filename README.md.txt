🔍 MedLens AI: Clinical Decision Support System
MedLens AI is a cloud-native medical portal designed to bridge the gap between historical patient data and real-time AI diagnostics. Built during the Kiro-spec hackathon, it leverages the power of Amazon Bedrock to provide doctors with instant clinical insights.

🚀 The Core Innovation
Unlike generic AI tools, MedLens AI uses a Retrieval-Augmented Logic approach:

Patient History: Securely fetched from Amazon DynamoDB.

Contextual Analysis: Combines historical records with current symptoms.

Bedrock Intelligence: Invokes Claude 3 (Haiku) to compare the patient's data against a simulated dataset of 5,000+ clinical cases.

🛠️ Tech Stack
Frontend: HTML5, Tailwind CSS, JavaScript (SPA Architecture).

Backend: AWS Lambda (Python 3.12).

API Layer: Amazon API Gateway (REST).

Database: Amazon DynamoDB (NoSQL).

AI Engine: Amazon Bedrock (Claude 3 Haiku).

🧩 Kiro Integration
This project followed the Kiro Spec-Driven Development model:

Used .kiro/specs/ to define the API contract between the frontend and backend teams.

Leveraged Kiro’s code-refactoring suggestions to transition from mock data to a live AWS Boto3 integration.

Documented infrastructure security (IAM Roles) within the Kiro workflow.

📦 Project Structure
Plaintext
├── index.html          # The Main Portal (Frontend)
├── lambda_function.py  # AWS Lambda Backend Logic
├── .kiro/              # Kiro Specs and Project Blueprints
└── README.md           # Documentation