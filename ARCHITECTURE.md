# MindWell Architecture

## Verified current shape

MindWell is a TanStack Start modular monolith with a browser dashboard, authenticated Cloud data access, a server-side streaming AI route, and a database-backed wellbeing history.

```text
Browser dashboard
  ├─ authenticated Cloud client + row-level access
  ├─ check-ins, reflections, feedback, doctors
  └─ server appointment workflow
       └─ verified professional + server-owned price/status/duration

AI companion
  └─ /api/chat → server-side Lovable AI Gateway → streamed response
```

The AI is a wellbeing companion. It does not diagnose, prescribe, determine dosage, or make autonomous clinical decisions.

## Boundaries

- `src/routes/` owns browser surfaces and HTTP endpoints.
- `src/lib/*.functions.ts` owns authenticated application workflows.
- `src/lib/*.server.ts` owns server-only provider helpers.
- Cloud row-level policies scope member data to its owner; role checks are server-side.
- Clinical and pharmacy operations are not delegated to the AI companion.

## Planned, not yet production-ready

The following are interfaces/backlog items, not claimed capabilities: Python inference service, model and dataset registries, safety policy registry, golden evaluation suite, calibration/OOD abstention, language-specific evaluation, rate limiting, payment webhooks, doctor dashboard, admin control plane, incident management, kill switches, canary/rollback automation, and comprehensive automated security/E2E tests.

## Next architectural slice

Complete the safety gateway and authenticated server workflows for every sensitive write before adding clinical or pharmacy surfaces.