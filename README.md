# SubWise Email Detection Logic (Convex snapshot)

This is a stable snapshot of the Gmail receipt parsing and subscription detection logic (Convex).

Highlights
- Safe Mode kill switch (crons blocked), manual scans allowed under caps
- Snapshot-gated parsing â†’ detection
- Pattern-based detection with charge evidence, refund/credit suppression, cancellation handling
- Aggregator extraction (Apple, Stripe, PayPal, Google Pay/Play)
- Nonâ€‘AI repair (Apple/Substack/PlayStation), INR handling
- Idempotent linking and blocklist for generic aggregators
- Calendar-accurate next billing roll-forward

Files
- convex/patternDetection.ts
- convex/repair.ts
- convex/utils.ts
- convex/emailScannerActions.ts
- convex/scanning/orchestrator.ts
- convex/emailCronJobs.ts
- convex/schema.ts
- convex/receiptParser.ts
- convex/adminQueries.ts
- COST_SAFETY_AND_UNIT_ECONOMICS.md

Notes: Logic snapshot for reference; not a runnable app.
