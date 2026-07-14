# AI-Powered Customer Feedback Analyzer

Turn unstructured customer reviews into actionable business insights using Google Gemini, FastAPI, Streamlit, and SQLite.

This application automatically analyzes customer feedback, identifies sentiment, assigns review scores, extracts key discussion themes, and presents results through an interactive dashboard. The solution follows a production-style architecture with a cloud-hosted FastAPI backend, Streamlit frontend, and persistent SQLite storage.

## Live Demo

**Frontend:** https://customer-review-analyzers.streamlit.app

**Backend API Docs:** https://customer-feedback-analyzer-genai.onrender.com/docs

---

# Table of Contents

- [Overview](#overview)
- [Business Problem](#business-problem)
- [Input Data](#input-data)
- [Key Features](#key-features)
- [Technology Stack](#technology-stack)
- [System Architecture](#system-architecture)
- [Application Workflow](#application-workflow)
- [Example Analysis](#example-analysis)
- [Database Design](#database-design)
- [Deployment Architecture](#deployment-architecture)
- [How to Run Locally](#how-to-run-locally)
- [Technical Skills Demonstrated](#technical-skills-demonstrated)
- [Results](#results)
- [Future Enhancements](#future-enhancements)
- [Author](#author)

---

# Overview

Customer feedback is one of the most valuable sources of business intelligence, but manually reviewing large volumes of reviews is time-consuming and difficult to scale.

This project leverages Generative AI to automate customer feedback analysis by transforming raw review text into structured insights that businesses can use to understand customer sentiment, identify recurring issues, and monitor customer satisfaction.

---

# Business Problem

Businesses receive customer feedback through websites, surveys, support channels, and review platforms.

As review volume grows:

- Manual review becomes inefficient
- Important insights are missed
- Sentiment labeling becomes inconsistent
- Recurring customer complaints remain hidden in large amounts of text

This project solves that challenge by automatically analyzing customer reviews and generating structured outputs that can be aggregated into business-level metrics.

---

# Input Data

The application accepts unstructured customer reviews submitted through:

- Streamlit Dashboard
- FastAPI API Endpoint

Each review is analyzed by Gemini and converted into structured business insights including:

- Sentiment Label
- Review Score
- Theme Classification

Example:

```text
The food was amazing and delivery was very fast.
```

Output:

```json
{
  "label": "positive",
  "score": 5,
  "theme": "delivery"
}
```

---

# Key Features

### AI-Powered Sentiment Analysis

Automatically classifies reviews as:

- Positive
- Neutral
- Negative

### Review Scoring

Assigns a score between 1 and 5 based on customer sentiment.

### Theme Extraction

Identifies the primary topic discussed in the review.

Examples:

- Delivery
- Service
- Food
- Quality
- Pricing
- Support

### Interactive Dashboard

Provides real-time business metrics including:

- Total Reviews
- Average Rating
- Positive Feedback Percentage
- Most Discussed Theme

### Historical Data Storage

Stores analyzed reviews in SQLite for future analysis and tracking.

### Cloud Deployment

Fully deployed application using:

- Render (Backend)
- Streamlit Community Cloud (Frontend)

---

# Technology Stack

| Layer | Technologies |
|---------|-------------|
| Frontend | Streamlit |
| Backend | FastAPI, Uvicorn |
| AI | Google Gemini API |
| Database | SQLite |
| Data Processing | Pandas |
| API Communication | Requests, Pydantic |
| Configuration | python-dotenv |
| Version Control | Git, GitHub |
| Deployment | Render, Streamlit Community Cloud |

---

# System Architecture

```text
User
 │
 ▼
Streamlit Dashboard
 │
 ▼
FastAPI REST API (Render)
 │
 ▼
Google Gemini
 │
 ▼
Structured JSON Response
 │
 ├── Dashboard Metrics
 └── SQLite Database
```

---

# Application Workflow

### 1. User Input

Users submit one or more customer reviews through the Streamlit dashboard.

### 2. API Communication

The frontend sends each review to the FastAPI backend hosted on Render.

### 3. AI Analysis

Google Gemini analyzes the review and generates structured output.

### 4. Response Generation

The backend returns:

```json
{
  "label": "positive",
  "score": 5,
  "theme": "delivery"
}
```

### 5. Dashboard Insights

The frontend aggregates results and generates business metrics.

### 6. Data Persistence

Results can be stored in SQLite for historical tracking.

---

# Example Analysis

### Input Review

```text
Customer support was rude and unhelpful.
```

### AI Output

```json
{
  "label": "negative",
  "score": 1,
  "theme": "service"
}
```

---

# Database Design

The SQLite database stores:

| Field | Description |
|---------|------------|
| review | Original customer review |
| label | Sentiment classification |
| score | AI-generated rating |
| theme | Main review topic |

This allows businesses to maintain a growing historical repository of customer feedback.

---

# Deployment Architecture

The application uses a multi-service cloud deployment architecture.

### Frontend Layer

Hosted on Streamlit Community Cloud.

Responsibilities:

- User interaction
- Dashboard rendering
- Business metrics reporting

### Backend Layer

Hosted on Render.

Responsibilities:

- Request validation
- Gemini integration
- Structured response generation
- API processing

### Communication Layer

The frontend communicates with the backend through REST API requests.

---

# How to Run Locally

### Clone Repository

```bash
git clone https://github.com/Sahajahanur/customer-feedback-analyzer-genai.git
cd customer-feedback-analyzer-genai
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Configure Environment Variables

Create a `.env` file:

```env
GOOGLE_API_KEY=your_google_api_key
```

### Start Backend

```bash
uvicorn api:app --reload
```

### Start Frontend

Open a second terminal:

```bash
streamlit run app.py
```

### Access Application

Frontend:

```text
http://localhost:8501
```

Backend Docs:

```text
http://localhost:8000/docs
```

---

# Technical Skills Demonstrated

### Artificial Intelligence

- Generative AI Integration
- Prompt Engineering
- Structured Output Generation
- LLM Application Development

### Backend Development

- FastAPI
- REST API Design
- Pydantic Validation
- JSON Processing

### Frontend Development

- Streamlit Dashboards
- Interactive User Interfaces
- Data Presentation

### Database Development

- SQLite
- Data Persistence
- Historical Data Tracking

### Cloud Engineering

- Render Deployment
- Streamlit Cloud Deployment
- Environment Variable Management

### Software Engineering

- Modular Project Architecture
- Git Version Control
- Multi-Service Deployment
- End-to-End Application Development

---

# Results

Successfully built and deployed a production-style AI application with:

- Public Streamlit frontend hosted on Streamlit Community Cloud
- Public FastAPI backend hosted on Render
- Gemini-powered sentiment analysis and theme extraction
- SQLite persistence layer for historical review storage
- End-to-end REST API communication between frontend and backend services

Validation completed using positive, negative, and neutral customer reviews to verify:

- Sentiment classification
- Review scoring
- Theme extraction
- Database storage
- Cloud deployment functionality

 <img width="957" height="770" alt="image" src="https://github.com/user-attachments/assets/6f1c77ca-1d9f-4b8b-bea6-14972a274adb" />

 <img width="977" height="787" alt="image" src="https://github.com/user-attachments/assets/4ec55ffd-76c6-4235-aa2c-c0f074e29f95" />

 

---

# Future Enhancements

- CSV Upload Support
- Batch Review Processing
- Interactive Visualizations
- PostgreSQL Integration
- Docker Containerization
- User Authentication
- Multi-Language Review Analysis
- Real-Time Analytics Dashboard

---

# Author

### Sahajahanur Laskar

Data Analyst | AI & Data Engineering Enthusiast

GitHub:
https://github.com/Sahajahanur

LinkedIn:
https://www.linkedin.com/in/sahajahanur-laskar/

Email:
connectingsrl@gmail.com

---

# Project Status

✅ Frontend Deployed

✅ Backend Deployed

✅ Gemini Integration Active

✅ Database Operational

✅ Production Ready
