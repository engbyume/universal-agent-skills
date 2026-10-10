# Person and fit references

## Sub-features

- Store optional body measurements with explicit units.
- Convert height and weight when the selected unit changes.
- Add separate face, body, and pose references from local synthetic images.
- Open a reference only after the user selects Open.

## How to get to it (user POV)

Open Person & Fit from the main navigation. Enter synthetic measurements or leave fields blank. Use Add face reference, Add body reference, or Add pose reference to choose a synthetic image.

## Driving it with agent-browser

1. Enter a synthetic height of 180 cm and weight of 70 kg.
2. Change height to inches and weight to pounds. Confirm the displayed values convert instead of only changing their unit labels.
3. Import `fitlab/.verification/fixtures/synthetic.png` through Add face reference, then import it through Add body reference.
4. Confirm both references appear in their own sections and that the app reports sanitized local storage.
5. Use only the synthetic fixture or another generated test image. Do not open or screenshot a human photo.

## Gotchas

- Blank measurements stay blank.
- Location metadata is always removed. Other metadata stays off unless the test explicitly changes the synthetic profile's setting.
- Photo unassignment clears a selection. It does not delete the stored image bytes.
