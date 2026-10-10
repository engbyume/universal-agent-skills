# Local workspace

## Sub-features

- Create a local profile with blank measurements.
- Review local-only storage, encryption, and metadata controls.
- Import reviewed JSON, CSV, or ZIP data and export a synthetic workspace.
- Delete a synthetic profile from the Privacy screen.

## How to get to it (user POV)

Open the app at `http://localhost:5173/`. Create the synthetic profile from onboarding. Use the main navigation to open Privacy for import, export, and deletion controls.

## Driving it with agent-browser

1. Open the isolated local origin in the headed `fitlab-synthetic` session.
2. Create `Synthetic verification profile` and leave measurements blank.
3. Open Privacy. Confirm the screen shows local storage, at-rest encryption, and stripped location metadata. Confirm external-provider consent is off.
4. Export synthetic JSON. Import a synthetic JSON fixture and verify the replacement warning appears before saving.
5. Delete only the synthetic profile. Verify that onboarding is visible again.

## Gotchas

- JSON does not carry photo bytes. Use ZIP when a synthetic backup includes images.
- JSON replacement and profile deletion change local records. Run them only at the isolated `localhost` origin with synthetic data.
- Never select the default origin or a user's profile during verification.
