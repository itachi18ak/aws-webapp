# 📨 AWS Lambda Contact Form Project

This project is a serverless contact form built using **AWS Lambda**, **API Gateway**, **DynamoDB**, and a **responsive HTML frontend**. The form collects user details and stores them securely in a DynamoDB table.


## 🚀 How It Works

### Frontend (HTML + CSS)

- A simple, mobile-friendly contact form (`contactus.html`)
- Submits data to an API Gateway endpoint mapped to your Lambda
- On success, redirects to `success.html` with a confirmation animation

### Backend (AWS Lambda)

- `GET` Request → Returns the contact form
- `POST` Request → Parses the form data and inserts it into DynamoDB
- Returns `success.html` upon successful submission

### DynamoDB

- A table (e.g., `aruntable`) stores each contact form submission
- Dynamically adds user entries with fields like `fname`, `lname`, `email`,'phone number','subject','contact method','country',`message`, etc.

---

## 🛠️ Setup & Deployment

### 🧱 Prerequisites

- AWS CLI configured
- IAM Role for Lambda with permissions:
  - `dynamodb:PutItem`
  - `logs:*`

### 📦 1. Upload Lambda Function

- Zip the Lambda code:
  ```bash
  zip function.zip lambda_function.py contactus.html success.html
