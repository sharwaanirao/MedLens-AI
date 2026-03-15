 Engineering Spec: MedLens AI Diagnostic Pipeline

1. Feature: Patient Longitudinal History Retrieval
User Flow: 
- Client sends `GET` request with `PatientID`.
- API Gateway routes to `MedLens_Logic` Lambda.
- Lambda executes `getItem` on DynamoDB Table.
- Returns `History` string to Frontend.
 2. Feature: Bedrock AI Clinical Inference
System Logic:
- Client sends `POST` request with JSON payload.
- Lambda extracts `Symptoms` and `History`.
- Prompt Engineering: 
  - Context: Clinical Assistant
  - Input: Combined longitudinal data
  - Constraint: Plain language explanation + Risk indicators.
- Model: Anthropic Claude 3 (via Amazon Bedrock).

3. Infrastructure (IaC)
- Database: DynamoDB (Partition Key: `PatientID`)
- Compute: Lambda (Runtime: Python 3.12)
- Security: IAM Role with `AmazonBedrockFullAccess` and `AmazonDynamoDBFullAccess`.
- Network: CORS Enabled for cross-origin local development.
