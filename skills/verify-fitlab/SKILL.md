---
name: verify-fitlab
description: Verify FitLab's local profile, closet, reference-photo, and outfit flows in a headed browser using synthetic data.
---

# FitLab Verification

Use this skill when changing or checking FitLab user flows. Use synthetic names, clothing labels, measurements, and images only. Never import a personal profile, wardrobe export, or human photo during verification.

Run verification at `http://localhost:5173/`. The `localhost` origin keeps the synthetic test profile separate from data at `http://127.0.0.1:5173/`. Keep the browser headed so the test remains visible and recoverable.

## Launch

From the repository root:

1. Install the app dependencies with `npm ci --prefix fitlab`.
2. Start the local server with `npm --prefix fitlab run dev`.
3. Open `http://localhost:5173/` in a headed browser session named `fitlab-synthetic`.
4. Create a profile named `Synthetic verification profile`. Use synthetic values only.

The development server binds to loopback. Do not use a public host, remote browser, or external image service for verification.

## Doctor

Run these checks from the repository root:

```sh
npm --prefix fitlab run typecheck
npm --prefix fitlab run test
npm --prefix fitlab run lint
npm --prefix fitlab run build
npm --prefix fitlab audit
```

Use `npm --prefix fitlab audit --omit=dev` for the production dependency check. Run `python3 scripts/validate_repo.py` before publishing public documentation.

The HEIC package can produce a build warning because it contains a Node-only branch. Treat HEIC support as verified only after a synthetic HEIC fixture imports in the headed local browser and the app reports a sanitized save.

## Drive

Choose a user-facing flow from `features/README.md`. Use semantic roles and accessible names. After each state-changing action, capture a fresh accessibility snapshot before choosing the next action.

Typical headed flow:

```sh
agent-browser --headed --session fitlab-synthetic open http://localhost:5173/
agent-browser --session fitlab-synthetic snapshot -i
```

Use the feature map's steps to create synthetic data, complete the flow, and check the visible result. Do not use profile data or photos from the default `127.0.0.1` origin.

## Evidence

Store synthetic verification evidence in `fitlab/.verification/`. Capture one screenshot and one accessibility snapshot for the feature under test. Name evidence with the feature and date, for example `closet-2026-10-10.png` and `closet-2026-10-10.aria.txt`.

```sh
mkdir -p fitlab/.verification
agent-browser --session fitlab-synthetic screenshot --full fitlab/.verification/closet-YYYY-MM-DD.png
agent-browser --session fitlab-synthetic snapshot -i > fitlab/.verification/closet-YYYY-MM-DD.aria.txt
```

Keep actions and observed results in the task report. Never include a user's name, real measurements, personal photo, photo filename, or exported profile in evidence. Confirm that each saved screenshot and snapshot contains synthetic data only.

## Cleanup

1. Delete the synthetic profile from the Privacy screen and confirm that the synthetic workspace is empty.
2. Close only the browser tab and local server created for this test. Keep the screenshot and accessibility snapshot in `fitlab/.verification/`.
3. Never delete, reset, or export a profile from `127.0.0.1:5173/`; that origin may contain the user's private data.
4. Remove only temporary files created by the current test. Keep canonical test fixtures and verification evidence.

## Helpers

- Local app commands and privacy notes: `fitlab/README.md`.
- User-facing flow map: `fitlab/.agents/skills/verify-fitlab/features/README.md`.
- Browser checks: use the installed `agent-browser` CLI in headed mode.
- Image fixture: use `fitlab/.verification/fixtures/synthetic.png`; do not use images from a Photos library.
- If an interaction fails, take a fresh accessibility snapshot and inspect the visible state before retrying.
