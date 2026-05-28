# Trial of the Century: Modern Cloud Architecture v. AI

## Project Overview

This project presents a cloud architecture solution for a fictional legal software startup called **ObjectionInspection**. The goal is to design and implement an AWS-based system that stores legal documents, uses **Amazon Bedrock** to generate summaries, and stores those summaries for future reference.

The solution focuses on simplicity, security, and alignment with AWS best practices.

---

## Scenario

ObjectionInspection needs an AI-powered workflow that can:

1. Accept legal documents as plaintext files
2. Store those documents securely
3. Send the document content to a foundation model hosted on **Amazon Bedrock**
4. Generate a summary of the document
5. Store the generated summary for later retrieval

For this project, legal documents are treated as simple plaintext files, and the emphasis is on demonstrating the architecture rather than optimizing model accuracy.

---

## Solution Architecture

### Core AWS Services Used

- **AWS IAM**
- **Amazon S3**
- **Amazon Bedrock**

### Optional Supporting Service
- **AWS Lambda** (if used to automate summarization)

---

## High-Level Architecture

The architecture follows this general flow:

1. A legal document is uploaded to an **Amazon S3 bucket**
2. A processing component retrieves the document content
3. The content is sent to **Amazon Bedrock**
4. Bedrock returns a generated summary
5. The summary is stored back in **Amazon S3**
6. Access is controlled using **IAM roles and policies** based on least privilege

---

## Architecture Explanation

### 1. Amazon S3
Amazon S3 is used as the storage layer for:
- Original legal documents
- Generated summaries

The bucket is kept **private** to follow security best practices. No public access is enabled.

### 2. Amazon Bedrock
Amazon Bedrock is used to access a foundation model capable of summarizing legal documents. The uploaded plaintext content is passed as input to the model, and the returned output is stored as the summary.

### 3. AWS IAM
IAM is used to securely control access between services. Permissions are scoped using the **principle of least privilege**, ensuring that only the required actions are allowed.

### 4. AWS Lambda (if used)
AWS Lambda can be used to automate the summarization workflow. For example:
- Trigger when a file is uploaded to S3
- Read the uploaded document
- Invoke Amazon Bedrock
- Save the summary back to S3

This avoids hard-coding secrets and supports a serverless design.

---

## Security Best Practices

This solution follows basic AWS security best practices:

- **No public S3 buckets**
- **Least privilege IAM permissions**
- No hard-coded credentials or secrets
- Controlled service-to-service access using IAM roles
- Separation of original documents and summaries through prefixes or folders in S3

Example S3 structure:

```text
s3://objectioninspection-legal-docs/input/
s3://objectioninspection-legal-docs/output/
