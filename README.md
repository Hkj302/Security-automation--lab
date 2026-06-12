# Cloud-Native SOAR & Automated Threat Triage Pipeline

## Project Overview
This project establishes an automated Incident Response pipeline that simulates brute-force attack telemetry, ingests the data via secure webhooks, and utilizes a cloud-native Security Orchestration, Automation, and Response (SOAR) platform to triage the event using an AI Analyst and generate tracking tickets.

## Tools & Technologies Used
* **SOAR Platform:** Tines
* **Telemetry & Automation:** GitHub Actions
* **Data Formats:** JSON, YAML
* **Protocols:** HTTPS (Webhook Ingestion via cURL)

## Architecture & Workflow
1. **Simulation:** A GitHub Actions workflow is manually triggered to simulate 100+ failed login attempts.
2. **Ingestion:** The telemetry data is securely forwarded across the internet using a POST request to a Tines Webhook URL.
3. **Triage:** The Tines SOAR platform captures the data packet and passes it to an integrated AI Agent.
4. **Ticketing:** The AI Agent normalizes the threat severity and auto-generates an issue tracking ticket within a simulated Jira environment.

## Engineering & Troubleshooting Milestones
* **Resolved Linux Syntax Errors:** Successfully debugged and resolved `exit code 3` string truncation and URL parsing errors during the cURL data-transit phase.
* **Pipeline Optimization:** Re-architected a flattened JSON payload structure within the YAML configuration to guarantee uncorrupted payload delivery.
