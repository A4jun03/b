# Security Status

## Implemented

- Publishable client configuration is the only browser database configuration.
- Service-role access is server-only and loaded inside privileged handlers.
- Role membership is kept in a separate role table and checked through a security-definer helper.
- Member-owned wellbeing records use row-level policies.
- Sensitive appointment fields are calculated by an authenticated server workflow.
- Browser access to prescription, generated prediction/trend, order, and notification creation is restricted.
- AI messages allow member-authored messages only; assistant/system writes are backend-controlled.

## Important limitations

- The existing public chat endpoint still needs a full authenticated/consent-aware safety gateway before it should handle persisted private conversations.
- Rate limiting, request correlation, abuse prevention, content classification, and structured security testing are not yet implemented.
- Appointment availability is checked before insert but does not yet have a database exclusion constraint or transaction-level reservation.
- Payments, prescription verification, uploads, and pharmacy fulfillment are not implemented.

## Never trust from the browser

User identity, role, doctor verification, appointment price/status/duration, prescription contents, order totals/status, discount values, and AI safety decisions must be derived or verified on the server.