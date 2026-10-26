# Pet360 — Proposed API Design

> These are suggested endpoint contracts, not a claim that these routes currently exist in the implementation.

## Conventions

- Base path: `/api/v1`
- Transport: HTTPS in deployed environments.
- Authentication: use the project's configured identity provider and verify credentials server-side.
- Content type: `application/json`, except supported upload routes.
- Return consistent error objects.
- Validate all IDs, query parameters, body fields, and file uploads.
- Calculate prices and permissions server-side; do not trust client totals or role fields.

## Suggested endpoints

| Method | Endpoint | Purpose |
|---|---|---|
| `GET` | `/health` | Liveness check; avoid exposing secrets |
| `GET` | `/api/v1/me` | Current authenticated user profile |
| `PATCH` | `/api/v1/me` | Update allowed profile fields |
| `GET` | `/api/v1/pets` | List pets owned by current user |
| `POST` | `/api/v1/pets` | Create a pet record |
| `GET` | `/api/v1/pets/:petId` | Read an owned pet record |
| `PATCH` | `/api/v1/pets/:petId` | Update an owned pet record |
| `DELETE` | `/api/v1/pets/:petId` | Delete an owned pet record, subject to retention policy |
| `GET` | `/api/v1/services` | Browse service listings |
| `GET` | `/api/v1/services/:serviceId` | View a service listing |
| `POST` | `/api/v1/appointments` | Request an appointment |
| `GET` | `/api/v1/appointments` | List current user's appointments |
| `GET` | `/api/v1/products` | Browse products, if e-commerce is implemented |
| `POST` | `/api/v1/orders` | Create an order, if checkout is implemented |
| `POST` | `/api/v1/ai/chat` | Submit a message to educational chat, if enabled |
| `POST` | `/api/v1/ai/image-analysis` | Submit a permitted image for demo analysis, if enabled |

## Example success response

```json
{
  "data": {
    "id": "example-id",
    "name": "Milo"
  }
}
```

## Example error response

```json
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Please check the submitted information."
  }
}
```

Do not expose stack traces, tokens, database connection strings, or provider error payloads to the client.

## Authorization rules

- A user may only access their own pet records and appointments unless a verified service role grants access.
- Admin privileges must be enforced on the server, not just hidden in the UI.
- Service providers should access only the records required to perform their assigned service.
- AI routes should have rate limits, payload limits, and abuse controls.

## API status

Before publishing implementation claims, compare this proposal with the real server routes and update the table to show which endpoints are implemented, tested, or planned.
