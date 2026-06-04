# Store Intelligence System - Purplle Tech Challenge 2026

## Overview
This repository contains the end-to-end Store Intelligence System pipeline designed for the Purplle Tech Challenge Round 2. It processes detection events to produce real-time store analytics, funnel logic, and anomalies.

## Requirements
- Docker
- Docker Compose

## How to Run (Acceptance Gate)

1. Make sure Docker Desktop is running on your machine.
2. Open your terminal in the root of this project.
3. Run the following command:
\`\`\`bash
docker-compose up --build
\`\`\`
4. The services will be available at:
   - **Frontend Dashboard**: http://localhost:3000
   - **Backend API & Swagger Docs**: http://localhost:8000/docs

## Documentation
- `DESIGN.md`: Contains system architecture and event schema.
- `CHOICES.md`: Outlines engineering decisions, trade-offs, and edge-case handling.
