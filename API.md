# API Inventory

## Implemented

- `POST /api/chat` — streams the authenticated product's current supportive companion response through the server-side AI gateway. The route validates that a message array is present and returns a service-unavailable response when the gateway key is missing.
- `requestAppointment` — authenticated server function. Accepts only a professional id, requested time, and requested consultation type; verifies the professional and derives price, duration, status, and owner server-side.

## Planned versioned boundaries

`/v1/chat`, `/v1/wellbeing`, `/v1/stress`, `/v1/risk`, `/v1/recommendations`, `/v1/appointments`, and `/v1/prescriptions` are architectural targets, not implemented endpoints.

## Error contract to complete

Future endpoints should return a safe error category and request identifier without stack traces, provider secrets, database internals, or private model paths.