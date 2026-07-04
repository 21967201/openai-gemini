# Gemini OpenAI Compatible Proxy - DEPRECATED

> **This project is deprecated.** Google now provides native OpenAI-compatible API endpoints.
> No third-party proxy is needed anymore.

## Migration Guide

Google Gemini API now natively supports OpenAI-compatible format:

### Endpoint
```
https://generativelanguage.googleapis.com/v1beta/openai/
```

### Usage
```bash
curl https://generativelanguage.googleapis.com/v1beta/openai/chat/completions \
  -H "Authorization: Bearer $GEMINI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gemini-2.5-flash",
    "messages": [{"role": "user", "content": "Hello"}]
  }'
```

### Supported Models
- gemini-2.5-pro, gemini-2.5-flash
- gemini-2.0-pro, gemini-2.0-flash
- gemini-2.0-flash-lite

### Supported Endpoints
- `/v1/chat/completions` (with streaming)
- `/v1/embeddings`
- `/v1/models`

### Python SDK
```python
from openai import OpenAI

client = OpenAI(
    api_key="your-gemini-api-key",
    base_url="https://generativelanguage.googleapis.com/v1beta/openai/"
)

response = client.chat.completions.create(
    model="gemini-2.5-flash",
    messages=[{"role": "user", "content": "Hello"}]
)
```

## Original Project
This was a Cloudflare Worker that proxied Gemini API to OpenAI format.
Now replaced by Google's native OpenAI compatibility layer.