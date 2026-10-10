# Outfit planner

## Sub-features

- Create looks and add, remove, edit, or reorder layers.
- Plan with Owned only, Mixed closet, Wishlist pieces, or Zero spend.
- Change pose, scene, camera, and lighting settings.
- Save a look and run the local layout-preview action.

## How to get to it (user POV)

Open Outfit Creator. Create a look, then add items from the tray or add a blank layer. Use the inspector to edit planning mode, layer order, pose, scene, camera, and light.

## Driving it with agent-browser

1. Create a synthetic look and add one Owned item.
2. Change pose and scene. Confirm the summary and layout update.
3. Add an Unknown layer while in Owned only. Confirm it is marked ineligible and Save look is disabled.
4. Change to Zero spend and confirm the same ineligible layer still blocks saving. Change to Mixed closet and confirm saving is allowed.
5. Save the look and choose Refresh Layout preview. Confirm the notice says that no image was generated or sent to a provider.

## Gotchas

- The preview is a generic layout preview. It is not a generated image or a photo of a person.
- Owned only and Zero spend exclude Unknown and Wishlist layers. Remove those layers or switch to Mixed closet before saving.
- Do not enable or call an external provider during verification.
