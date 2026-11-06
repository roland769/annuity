# Annuity Income Estimator

Single-page lead-generation funnel for Facebook Ads: age, sex, investment amount, state and income start date → estimated monthly income range → quote request form.

- `index.html` — the whole funnel (no dependencies, no external requests; ~14 KB).
- Estimates are interpolated from annuity.org's published $100,000 SPIA payout table (September 2026) and shown as a −20 % / +10 % range.

## Before going live

1. Replace `Elevate SMG` and the two `example.com` links in the Privacy & Contact Agreement with your company name, privacy policy and disclaimer.
2. In `index.html`, find the `TODO` in the lead-form submit handler and send the `lead` object to your CRM / webhook / dialer, and fire your Meta Pixel `Lead` event there.
3. Host on your own domain with gzip/brotli; load the Meta Pixel `async`.
