# ScamSOS India

A guide for the first hour after an online scam in India: what to do, one-tap call to 1930,
a calm-down screen, a voice assistant, and a report + bank letter + proof pack builder.
Optional accounts let a person save reports; a demo "police desk" lists saved reports.

Independent guide, not a government service. It does not file complaints; always call 1930
and report on https://cybercrime.gov.in.

## Files
- index.html        the app (works on its own, nothing to set up)
- how-it-works.html info page
- account.html      register / login / victim dashboard / police desk (needs Supabase)
- schema.sql        database + access rules for Supabase (PostgreSQL)

## Publish free (GitHub Pages)
1. Supabase: create a free project, SQL Editor -> paste schema.sql -> Run.
2. Project Settings -> API: copy Project URL and anon key into the top of account.html
   (replace the two PASTE_YOUR placeholders). Never use the service_role key.
3. GitHub: new PUBLIC repo, upload index.html, account.html, how-it-works.html (same folder).
4. Settings -> Pages -> Deploy from a branch -> main / (root).
5. Open https://<your-username>.github.io/<repo>/ , register, then in Supabase SQL Editor run:
   update public.profiles set role='police'
     where id=(select id from auth.users where email='your-email@example.com');

## Before sharing widely
- Re-verify 1930, cybercrime.gov.in, sancharsaathi.gov.in, cms.rbi.org.in and the bank-letter wording.
- Add a privacy notice and consent text: accounts store names, phones and fraud details.
- The AI voice chat only runs inside Claude; on your own site Talk uses the built-in step-by-step flow.
