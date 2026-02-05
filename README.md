# Konflux Demo - Hello World Go Application

## Purpose

This is a simple Go "Hello World" application for demonstrating Konflux CI/CD pipelines.

> **Note**: This is the `fixed-vulnerabilities` branch with up-to-date dependencies. The `main` branch intentionally contains outdated/vulnerable dependencies for security scanning demos.

## Current Versions

### Go Version
- **Go 1.22** - Current stable release

### Dependencies
- **github.com/gin-gonic/gin v1.10.0** - Latest Gin web framework
- **github.com/sirupsen/logrus v1.9.3** - Latest logrus logging library

### Docker Base Images
- **golang:1.22-alpine** - Current Go build image
- **alpine:3.21** - Current Alpine runtime image

## Application Details

Simple HTTP server with two endpoints:
- `GET /` - Returns "Hello, World!" JSON response
- `GET /health` - Health check endpoint

Server runs on port 8080.

## Building and Running

### Local Development
```bash
# Install dependencies
go mod download

# Run the application
go run main.go

# Test the endpoint
curl http://localhost:8080
```

### Docker Build
```bash
# Build the image
docker build -t konflux-demo:latest .

# Run the container
docker run -p 8080:8080 konflux-demo:latest

# Test the endpoint
curl http://localhost:8080
```

## License

This is a demo project for testing purposes only.
