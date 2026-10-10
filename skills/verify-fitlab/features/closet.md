# Closet

## Sub-features

- Create and edit clothing or accessory entries.
- Keep Owned, Suggested, Wishlist, and Unknown states explicit.
- Search and filter the closet by category and ownership.
- Import sanitized local images or mapped CSV records.

## How to get to it (user POV)

Open My Closet from the main navigation. Choose New item to add a synthetic entry. Use the search box and category or ownership filters to find it.

## Driving it with agent-browser

1. Create a synthetic item named `Synthetic blue shirt` with category Shirt, ownership Owned, and color blue.
2. Verify the closet card shows its name, category, ownership, and color.
3. Edit the item to change its color, then search for its name and confirm the updated card remains visible.
4. Switch the Ownership filter to Wishlist, then Unknown, and confirm the Owned item is not shown in either filtered result.
5. If checking image import, use only `fitlab/.verification/fixtures/synthetic.png` and confirm the sanitized-save notice.

## Gotchas

- A filename is not an ownership signal. Keep the explicit ownership value from the form or import.
- Image imports are re-encoded locally before storage. A failed conversion must not store the source file.
- Do not use a real closet export or personal photo to populate the synthetic test profile.
