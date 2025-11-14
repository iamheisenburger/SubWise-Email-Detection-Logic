SubWise Email Detection Logic Snapshot

What this repo is
- Stable, vendorable snapshot of SubWise’s Convex-based detection pipeline for receipts → subscriptions.
- Used as a fallback reference for future chats and as a reproducible baseline.

What’s inside
- convex/patternDetection.ts — pattern-based detection, refund/cancellation/credit suppression, cadence inference, next billing date.
- convex/repair.ts — non-AI repair/salvage (Apple/Stripe/PayPal/Google/PlayStation), newest-first processing.
- convex/emailScannerActions.ts — Gmail scan + snapshot-gated “repair → detect” finalizer.
- convex/scanning/orchestrator.ts — scan lifecycle, locks, checkpoints.
- convex/receiptParser.ts, convex/utils.ts — parser + helpers.
- COST_SAFETY_AND_UNIT_ECONOMICS.md — cost-safety rules and runbook.

How to use this snapshot
- Treat this repo as a read-only baseline. Pin to a stable tag in consumers (recommended).
- To roll back or re-use logic, copy files under convex/ into the target Convex project’s convex/ directory.

Release pointers (canonical)
- Branch: release/2025-11-14-stable
- Tag: v1.0.0-stable

Pin from your main app (option A: git submodule, pinned to tag)

    git submodule add https://github.com/iamheisenburger/SubWise-Email-Detection-Logic.git vendor/SubWise-Email-Detection-Logic
    git -C vendor/SubWise-Email-Detection-Logic checkout v1.0.0-stable
    git add .gitmodules vendor/SubWise-Email-Detection-Logic
    git commit -m \"chore: pin detection logic snapshot @ v1.0.0-stable\"

Pin from your main app (option B: copy-in vendor drop)
- Copy convex/* into your app’s convex/ and commit. Keep the tag noted in your commit message.

Notes on public vs private
- Public makes it trivial for new chats/tools to read without credentials.
- Private is fine if your PAT/MCP server is configured; just ensure repo scope is granted.

Cost-safety reminder
- Follow COST_SAFETY_AND_UNIT_ECONOMICS.md before enabling any automation.

# SubWise-Email-Detection-Logic