# Aps-Automation-Api_Docs - Rate Limits

**Pages:** 2

---

## servicelimits/:owner

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/servicelimits-owner-PUT/

**Contents:**
    - Jump To
- servicelimits/:owner
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Request
- Body Structure
  - Response

User can only update the following 2 properties:

LimitProcessingTimeSec cannot be set greater than the maximum processing time limit specified by the engine.

Successfully create a new service limits configuration.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
application/json
```

Example 3 (json):
```json
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/servicelimits/:owner' \
  -X 'PUT' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "backendLimits": {
          "Revit": {
            "limitProcessingTimeSec": 150
          }
        }
      }'
```

Example 4 (json):
```json
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/servicelimits/:owner' \
  -X 'PUT' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "backendLimits": {
          "Revit": {
            "limitProcessingTimeSec": 150
          }
        }
      }'
```

---

## servicelimits/:owner

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/servicelimits-owner-GET

**Contents:**
    - Jump To
- servicelimits/:owner
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Response
- HTTP Status Code Summary
  - Response

Gets a user’s service limit configuration.

Successfully get the service limits configuration.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/servicelimits/:owner' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/servicelimits/:owner' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 4 (json):
```json
{
  "frontendLimits": {
    "limitPayloadSizeInKB":64,
    "limitVersions": 100,
    "limitAliases": 100,
    "limitPublicAliases": 0,
    "limitAppUploadSizeInMB": 100
  },
  "backendLimits": {
    "Revit": {
      "limitProcessingTimeSec": 150,
      "limitTotalUncompressedAppsSizeInMB": 500
    }
  }
}
```

---
