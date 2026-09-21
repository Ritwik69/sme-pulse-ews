# SME Pulse — Early Warning System (Static Demo)

A fully static demo of an Early Warning System for an Indian NBFC's SME secured-lending
book (LAP / secured business loans), styled after an Aditya Birla Capital-scale portfolio.
No backend, no build step, no dependencies — open `index.html` or visit the hosted page.

**Live:** https://ritwik69.github.io/sme-pulse-ews/

## What's inside
- **Portfolio overview** — book size, GNPA, flagged counts by band, 6-month exposure-at-risk
  trend, risk by product / industry / region, channel-wise flag rate, and signal coverage.
- **Watchlist** — flagged accounts ranked by exposure × score, sortable columns, product and
  band filters, and a prominent **Pre-delinquency** filter (stressed but still current on EMIs).
- **Drill-down** — 12-signal breakdown grouped by source (Repayment · LMS / Cash-flow ·
  Account Aggregator / External), 12-month DPD and 6-month score sparklines, and a co-pilot
  panel with a plain-English assessment, recommended action, and free-form Q&A.

## Scoring (transparent, in-page)
A weighted 0–100 composite from 12 signals — DPD trend, EMI bounces, EMI-to-inflow ratio,
AA inflow change, turnover decline, bureau drop, GST delay, new unsecured borrowings, MCA
charges, EPFO delay, legal/Sec-138 flags, and (SCF only) anchor payment delay. Bands:
red ≥ 65 · amber 45–64 · watch 30–44. Any account at 60+ DPD floors into the red band.

## Co-pilot
The drill-down co-pilot can call a small backend that proxies the Anthropic API for a
live, natural-language assessment. **This hosted build is static and has no backend**, so
the co-pilot automatically and silently uses its precomputed rule-based explanation and
prepared Q&A instead — no errors, no broken panels. (The API key, when used, lives only
server-side and is never shipped to the browser.)

## Data
All 5,000 accounts are synthetic and generated with a fixed seed. Risk is not random —
every signal is correlated through a single latent stress factor per account, calibrated to
~1.3% Stage-3 GNPA. No real borrower data is used.
