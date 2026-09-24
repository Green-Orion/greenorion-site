# Tee Apart — launch notes (no domain, page at greenorion.net/teeapart/)

Name: **Tee Apart** since 2026-09-22 ("GO Golf" is taken as an app name and every TLD). The page moved to /teeapart/ with the name; the Formspree tag `[gogolf-waitlist]` and the repo name `go-golf` keep the old slug — plumbing nobody sees.

## 1. Names to reserve now (free, five minutes each)
- Instagram: handle to be chosen for Tee Apart (the `@gogolf…` candidates in `marketing/handles.csv` are void with the rename). Bio links to greenorion.net/teeapart/.
- Same handle on TikTok and X even if unused — stops squatters, keeps the name consistent.
- Reddit: post from a personal account in r/SGGolfers when TestFlight opens; do not create a brand account.
- Apple: the App Store Connect record "Tee Apart" exists (created 2026-09-22, bundle `net.greenorion.golf`, 1.0 Prepare for Submission) — nothing to do before the first TestFlight build.
- Domain: not needed for launch. teeapart.com / teeapart.app were unregistered at the 09-15 check and not bought; if bought later, 301 to greenorion.net/teeapart/ (or the reverse).

## 2. TestFlight public-link flow
1. App Store Connect -> app -> TestFlight -> upload a build (Xcode Organizer or `xcrun altool`).
2. First external build needs Beta App Review (usually 24-48 h). Fill in beta description + contact email.
3. Create an External group ("Waitlist"), enable **Public Link**, set a tester cap (start at 100).
4. Reply to each waitlist email with the public link — one email per batch, BCC, from sander@greenorion.net.
5. Builds expire after 90 days; ship a new build at least every 60 days or testers get locked out.
6. Once the link is live, replace the "Coming to TestFlight" copy on the page with the link. Do not
   add an App Store badge until the app is actually on the App Store.

## 3. Mailbox rule
- Every waitlist submission arrives via Formspree (form id mvzwazrr) with subject **`[gogolf-waitlist]`**,
  fields: name, email, home_course, source.
- Create an Outlook rule: subject contains `[gogolf-waitlist]` -> move to folder "Tee Apart / Waitlist".
- Main-site contact form mail is unchanged (subject is Formspree's default) so the two streams never mix.
- Formspree free tier: 50 submissions/month across BOTH forms. Upgrade or watch the count once
  Instagram traffic starts.
- Keep a simple sheet (name, email, home course, date, invited Y/N). Formspree keeps 30 days of history only.

## 4. What to measure (site currently measures nothing)
Recommendation: **Cloudflare Web Analytics** — free, no cookies, no consent banner needed, works on GitHub
Pages because it is a single script tag with no server side. Plausible is the paid alternative (USD 9/mo)
if you want goals/funnels without self-hosting.

Snippet (NOT added to the page — Sander's call). Sign in at dash.cloudflare.com -> Web Analytics ->
Add a site -> hostname `greenorion.net` -> copy the token into `data-cf-beacon`, then paste before `</body>`
in BOTH index.html files:

```html
<!-- Cloudflare Web Analytics -->
<script defer src='https://static.cloudflareinsights.com/beacon.min.js'
        data-cf-beacon='{"token": "PASTE_TOKEN_HERE"}'></script>
<!-- End Cloudflare Web Analytics -->
```

Metrics that matter for a waitlist page, in order:
1. Waitlist submissions per week (count `[gogolf-waitlist]` mails — the only number that really counts).
2. Page views of /teeapart/ and referrer split (Instagram vs direct vs Reddit) — from the analytics tool.
3. Conversion = submissions / page views. Below 3 % after 200 views: rewrite the hero or the form.
4. Later: TestFlight installs and sessions (App Store Connect shows both, per build).

## 5. Before going public — checklist
- [ ] Push the branch, confirm https://greenorion.net/teeapart/ renders (GitHub Pages serves the folder index).
- [ ] Submit the form once yourself; confirm the mail lands with subject `[gogolf-waitlist]`.
- [ ] Set the Outlook rule (section 3).
- [ ] Reserve the Instagram handle; post one image of the page or the emblem, bio link set.
- [ ] Decide on analytics (section 4) and, if yes, add the snippet to both pages.
- [ ] Share the page with the original Ryder Cup group first — they are testers batch 1 and the honest critics.
- [ ] Add `og:image` that is a real 1200x630 graphic once one exists; today it points at the GO emblem PNG.
