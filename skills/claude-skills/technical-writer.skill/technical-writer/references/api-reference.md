# API Reference Template

Use this template for documenting REST APIs, GraphQL endpoints, RPC methods, SDK functions,
and library APIs. Each endpoint or function gets its own self-contained section.

---

## Single Endpoint / Function Block

```markdown
## `METHOD /path` or `functionName()`

One-sentence summary of what this does. Start with a verb.

**Requires authentication** / **Public endpoint** (delete whichever doesn't apply)

### Parameters

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `param_name` | `string` | Yes | What it is and any constraints (max length, format, etc.) |
| `another_param` | `integer` | No | Default: `0`. What it does. |

### Request Body (if applicable)

```json
{
  "field": "value",
  "nested": {
    "key": "value"
  }
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `field` | `string` | Yes | Description |

### Response

**Success — `200 OK`** (or appropriate status code)

```json
{
  "id": "abc123",
  "status": "active",
  "created_at": "2024-01-15T10:30:00Z"
}
```

| Field | Type | Description |
|-------|------|-------------|
| `id` | `string` | Unique identifier |
| `status` | `string` | One of: `active`, `inactive`, `pending` |
| `created_at` | `string` | ISO 8601 timestamp |

### Errors

| Status | Code | Description |
|--------|------|-------------|
| `400` | `invalid_param` | A required parameter is missing or malformed |
| `401` | `unauthorized` | Missing or invalid authentication token |
| `404` | `not_found` | Resource does not exist |
| `429` | `rate_limited` | Too many requests. Retry after `Retry-After` seconds |

### Example

```bash
curl -X POST https://api.example.com/v1/resource \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"field": "value"}'
```

```json
{
  "id": "abc123",
  "status": "active",
  "created_at": "2024-01-15T10:30:00Z"
}
```
```

---

## Full API Reference Document Structure

```markdown
# API Reference

Brief overview of the API — what it does, base URL, versioning approach.

**Base URL:** `https://api.example.com/v1`
**Authentication:** Bearer token via `Authorization` header
**Rate limits:** 1,000 requests/minute per token

## Authentication

How to obtain and use credentials.

## Endpoints

### Resource Name

Brief description of this resource group.

#### `GET /resource`
...

#### `POST /resource`
...

#### `GET /resource/{id}`
...

## Error Handling

General explanation of error response format:

```json
{
  "error": {
    "code": "invalid_param",
    "message": "Human-readable description",
    "param": "field_name"
  }
}
```

## Pagination (if applicable)

How pagination works — cursor-based, offset, etc.

## Changelog

Link to or embed a brief log of breaking changes by version.
```

---

## AI Agent-Specific Guidance

When the audience is an AI agent, prioritize:

1. **Typed signatures at the top** of each section, before any prose.
2. **Enum values listed explicitly** — never "one of several options."
3. **Every field documented** — no "additional fields may be present."
4. **Error codes as constants** — not prose descriptions alone.
5. **Complete, copy-pasteable examples** for every endpoint.
6. **No cross-references** — each section must stand alone.
