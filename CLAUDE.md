# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Purpose

This is a simple Go "Hello World" application for demonstrating Konflux CI/CD pipelines.

> **Branch note**: This is the `fixed-vulnerabilities` branch with current dependencies. The `main` branch intentionally contains outdated/vulnerable dependencies for security scanning demos.

## Build and Run Commands

```bash
# Install dependencies
go mod download

# Run the application
go run main.go

# Build Docker image
docker build -t konflux-demo:latest .

# Run Docker container
docker run -p 8080:8080 konflux-demo:latest

# Test endpoints
curl http://localhost:8080        # Hello World
curl http://localhost:8080/health # Health check
```

## Architecture

Single-file Go web server (`main.go`) using Gin framework with two HTTP endpoints:
- `GET /` - Returns JSON greeting
- `GET /health` - Health check

Server listens on port 8080. Multi-stage Dockerfile builds a static binary and runs in Alpine.
