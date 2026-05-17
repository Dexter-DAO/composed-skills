# Endpoint Catalog

## x402.dexter.cash

Base URL: `https://x402.dexter.cash`

### x402.dexter.cash — $0.01

**Endpoint:** `POST /api/v2-test`

**Request body:**
```json
{
  "type": "http",
  "method": "POST",
  "discoverable": true,
  "bodyType": "json",
  "bodyFields": {}
}
```

**Response:**
```json
{
  "ok": {
    "type": "boolean"
  },
  "message": {
    "type": "string",
    "description": "Confirmation that the handler ran after payment verification."
  },
  "timestamp": {
    "type": "string",
    "description": "ISO timestamp when the response was generated."
  }
}
```

