# Testing Human+ on EQ Bench 3

**Note:** This guide describes the testing methodology used by the author. The main Human+ API is not publicly available. This documentation is provided for reference and for those who may have access to a hosted API endpoint.

## Overview

EQ Bench 3 expects models to be accessible via an API that matches the OpenAI chat completions format. To test Human+, you'll need:

1. **Access to a Human+ API endpoint** (hosted by the author or your own deployment)
2. **EQ Bench 3 configured** to call the Human+ API
3. **API credentials** (if authentication is required)

## Option 1: Using Hosted Human+ API

If a hosted Human+ API is available:

### Configuration

Set these environment variables in your `.env` file or environment:

```bash
TEST_API_KEY=your-provided-api-key  # If authentication is required
TEST_API_URL=https://humanplus-api.example.com/v1/chat/completions
```

### Running EQ Bench 3

```bash
cd eqbench3_integration
python eqbench3.py --model humanplus/engine --iterations 1
```

EQ Bench 3 will automatically call your configured API URL.

## Option 2: Deploying Your Own Instance

If you have access to the Human+ implementation and want to deploy your own API:

### Requirements

- Human+ implementation code
- Anthropic API key (for Claude backend)
- Web server (Flask, FastAPI, etc.)
- Hosting platform (Railway, Render, Fly.io, etc.)

### API Interface

The API must implement the OpenAI chat completions format:

**Endpoint:** `POST /v1/chat/completions`

**Request:**
```json
{
  "model": "humanplus/engine",
  "messages": [
    {"role": "user", "content": "Hello"}
  ],
  "temperature": 0.7,
  "max_tokens": 4000
}
```

**Response:**
```json
{
  "choices": [{
    "message": {
      "role": "assistant",
      "content": "Response text here"
    },
    "finish_reason": "stop"
  }],
  "model": "humanplus/engine"
}
```

### Deployment Platforms

Popular options for hosting:

- **Railway** - Easy setup, free tier available
- **Render** - Simple deployment, free tier (spins down after inactivity)
- **Fly.io** - Good performance, free tier
- **AWS/GCP/Azure** - Enterprise-grade, more complex setup

### Environment Variables

Your deployment will need:
- `ANTHROPIC_API_KEY` - For Claude API access
- `PORT` - Server port (usually set by platform)

## Configuration for EQ Bench 3

### Environment Variables

```bash
# In .env file or environment
TEST_API_KEY=your-api-key  # If using authentication
TEST_API_URL=https://your-api-url.com/v1/chat/completions
```

### Running Tests

```bash
# Quick test (rubric only)
python eqbench3.py --model humanplus/engine --iterations 1

# Full ELO test
python eqbench3.py --model humanplus/engine --iterations 5
```

## Results

Results will be saved to:
- `results/eqbench3/` - ELO scores and detailed results
- `logs/eqbench3/` - Interaction logs

## Troubleshooting

### API Connection Issues

- Verify `TEST_API_URL` is correct
- Check API key if authentication is required
- Ensure the API endpoint is accessible from your network

### Timeout Errors

- Increase `REQUEST_TIMEOUT` in EQ Bench 3 configuration
- Check API server logs for performance issues

### Authentication Errors

- Verify `TEST_API_KEY` matches the API's expected format
- Check if the API requires Bearer token authentication

## Contact

For access to a hosted Human+ API or questions about deployment, please contact the author.
