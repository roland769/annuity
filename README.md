# Annuity Income Estimator

Single-page lead-generation funnel for Facebook Ads: age, sex, investment amount, state and income start date → estimated monthly income range → quote request form.

- `index.html` — the whole funnel (no dependencies, no external requests; ~14 KB).
- Estimates are interpolated from annuity.org's published $100,000 SPIA payout table (September 2026) and shown as a −20 % / +10 % range.

## Before going live

1. Replace `Elevate SMG` and the two `example.com` links in the Privacy & Contact Agreement with your company name, privacy policy and disclaimer.
2. Form submissions are POSTed as JSON to the GoHighLevel inbound webhook set in `WEBHOOK` (in `index.html`). The Meta Pixel (2055287805271330) is in the page head; `PageView` fires on load and `Lead` fires on quote-form submit only for qualified leads (investment amount ≥ $250,000).
3. After the quote form is sent, the page redirects to `/typ` (investment amount ≥ $250,000) or `/typ-nq` (below). Create both pages on the same domain.
4. Host on your own domain with gzip/brotli; load the Meta Pixel `async`.
