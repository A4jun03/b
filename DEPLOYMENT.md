# Deployment Notes

The app runs as a TanStack Start application with the existing Vite configuration and Cloud backend integration.

Required server-side configuration includes the Cloud database URL, publishable key, and `LOVABLE_API_KEY` for the AI companion. Service-role credentials must remain server-only and must never be placed in browser-visible variables.

The current preview is not a claim of production readiness. Add security headers, rate limits, database backup/restore verification, monitoring, payment webhook verification, and end-to-end tests before launch.