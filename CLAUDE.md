# Strawberry Media Pages repo

Live at https://reports.strawberrymedia.com.au (also strawberrymedia.github.io). This repo is PUBLIC.

## How it works

- Originals go in `public-encrypted/`. It stays on this Mac: gitignored, and the lefthook check blocks any commit that stages it.
- Every commit locks new or changed pages from `public-encrypted/` into `public/` (StatiCrypt). Only `public/` publishes.
- Folder path in `public/` = web address. Keep file names steady once a client has a link: renaming changes the address and the password.
- Master secret: `ENCRYPT_SECRET` in `~/strawberry-media/.env` (copy in NordPass: "Strawberry Media – Pages encryption master secret"). `scripts/encrypt/encrypt_public.py` reads only that line. Never print it.
- Page passwords: Trinity runs `python3 scripts/encrypt/encrypt_public.py --show --reveal` in her own Terminal. Never run `--reveal` in a Claude session.

## Lock or public

Lock (save in `public-encrypted/`):

- Client reports and dashboards with any figures: spend, leads, bookings, conversion rates, revenue.
- Pollinate Health ads and website reports.
- Proposals and anything with fees or rates.
- Strategy documents, audits, campaign briefs.
- Anything a competitor or the public shouldn't see.

Public (save straight in `public/`):

- Test pages (e.g. `hello.html`).
- Strawberry Media portfolio and service pages.
- Case studies with the numbers removed.

If unsure, lock it.

## Never publish

- Patient names or any patient detail, even locked.
- Slate Accounts' client data or bookkeeping material, even locked.
- Lead names, emails or phone numbers. Reports show totals only.

## Layout

- One folder per client: `clients/slate/`, `clients/ladybird/`, `pollinate/`.
- No `index.html` at the top, so the bare address shows nothing to browse.
- Publish only what Trinity has approved. Drafts stay in the project repos.

## Sharing

- Send the link and the password separately: link by email, password by text or another channel.
- Send the https link, never a file:// one. Check it in a private window first.
