# Acceptance and security criteria

- Responsive design tested at common mobile, tablet and desktop widths; keyboard and screen-reader navigation; reduced motion support.
- Actual RFQ basket with add/remove, editable quantities, model variants and validation.
- Backend must persist valid inquiries only when properly configured; avoid a success message if delivery fails.
- Admin data access server-authorized and audited; database policies must not expose private leads.
- Server-side input validation, sensible rate limits, bot protection and non-exposing error messages.
- Do not check `.env`, API keys, customer information or third-party credentials into GitHub.
- If imagery is AI-created, do not misrepresent it as verified staff, real inventory or live safety conditions.
- Supplier certificates, PPE ratings, emergency escape performance and standards must be verified against official current manufacturer literature before display.
- Tests: component behavior, quote calculations, API validation, successful and failed notifications; lint/typecheck/build.
