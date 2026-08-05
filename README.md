# RAG Agent Logging and Monitoring System

## Overview

This project enhances a Retrieval-Augmented Generation (RAG) agent by adding a logging and monitoring layer for tracking system performance, token usage, errors, and response latency.

The system records every user request and LLM response into Google Sheets and uses a separate n8n monitoring workflow to detect threshold breaches and send Slack alerts.

## Features

- Request and response logging
- Token usage tracking (input, output, total tokens)
- Response latency monitoring
- Error logging with failure details
- Google Sheets as logging storage
- Automated monitoring workflow using n8n
- Slack alerts for:
  - Daily token usage threshold breach
  - High error rate detection
- Alert deduplication to prevent repeated notifications

## Workflow Components

### 1. RAG Agent with Logging

The RAG workflow captures:
- User query
- Retrieved context
- Generated response
- Token consumption
- Execution status
- Error messages
- Response latency

All records are stored in Google Sheets.

### 2. Monitoring and Alerting Workflow

The monitoring workflow:
- Runs periodically using n8n Schedule Trigger
- Reads logs from Google Sheets
- Calculates daily token usage
- Checks recent error occurrences
- Sends Slack notifications when thresholds are exceeded

## Tools Used

- n8n
- Google Sheets
- Slack Incoming Webhook
- OpenAI API / LLM API
- Python (for RAG processing)

