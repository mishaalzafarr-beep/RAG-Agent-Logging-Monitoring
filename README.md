# RAG Agent with Logging & Monitoring

## Overview

This project implements a Retrieval-Augmented Generation (RAG) agent with logging, monitoring, and alerting using n8n.

The system retrieves relevant knowledge-base information, generates responses, records execution metrics, and monitors operational health.

## Features

- RAG-based question answering
- Knowledge-base retrieval using vector search
- Token usage tracking
- Response latency tracking
- Success and error logging
- Google Sheets logging
- Automated monitoring workflow
- Daily token usage alerts
- Error-rate spike alerts
- Alert deduplication to prevent repeated notifications

## Monitoring Thresholds

- Daily token usage: **7,500 tokens**
- Error spike window: **1 hour**
- Error spike threshold: **5 errors**
- Monitoring interval: **10 minutes**

## Technologies

- n8n
- Supabase / pgvector
- Google Sheets
- OpenRouter / LLM APIs
- Slack Webhooks

## Workflows

### RAG Agent

Handles user queries, retrieves relevant knowledge-base content, generates responses, and records execution metrics.

### RAG Monitoring & Alerts

Runs periodically, analyzes logged executions, calculates token usage and recent errors, and sends Slack alerts when configured thresholds are exceeded.

## Logging

The logging layer records:

- Timestamp
- User Query
- Retrieved Snippets
- Generated Answer
- Input Tokens
- Output Tokens
- Total Tokens
- Status
- Error Message
- Response Latency

## Alerting

The monitoring workflow sends alerts when:

- Daily token usage exceeds 7,500 tokens.
- At least 5 errors occur within the last hour.

Alert deduplication prevents repeated token alerts during the same day and repeated error alerts while the same error spike remains active.
