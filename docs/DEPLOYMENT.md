# Deployment

Recommended architecture: GitHub `main` → Vercel auto-deploy → Next.js site; Supabase for approved RFQ data storage.

1. Connect this repository to Vercel and assign the production branch `main`.
2. Configure public app base URL and Supabase project URL/anon key through platform secrets, not commits.
3. Configure any privileged Supabase service role key **server-side only**, never `NEXT_PUBLIC_`.
4. Set verified notification email provider secrets and allowed sender domain.
5. Create and apply vetted database migrations, row-level security and server-side authorization.
6. Verify staging deployment and form delivery before connecting production domain.
7. Set up SPF, DKIM and DMARC with authorized DNS access; test deliverability independently.
8. Deploy only after user approval of production domain changes.

`main` is a documentation/bootstrap repository right now; nothing is deployed by these commits.
