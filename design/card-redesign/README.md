# Implemented: Clásica limpia (option A)

Approved by the user and implemented in index.html. Original comparison: comparison.png.

## Result

- implemented-sheet.png: actual production card renderer, enlarged for review.
- implemented-mobile.png, implemented-captain.png, implemented-dark.png: browser screenshots of the game.
- Baraja and Capitán faces share the `.card` component: 39 × 54 px; mini cards 32 × 45 px. The CSS inset frame is always 2 px with the same 0.6 px declared border, independent of illustration.
- Large upright rank/suit indices at top-right and bottom-left; small score preserved at bottom-right. Pocha still hides points.
- Existing SUIT_IMG artwork is unchanged. Numbered cards render exact pip counts; the ace has one central suit image.
- Twelve original court illustrations, with a separate suit-specific figure for each rank. Twelve matching Capitán illustrations. Art is transparent; borders, labels, points and pip arrangements remain code-driven.
- Special-card captions stay outside the face for legibility; inventory, detail panel, public seat icons and chest reveal use the same face renderer. Chest artwork itself is unchanged.

## Assets and generation

Built-in image_gen generated both production atlases:
- ../../assets/classic/courts.png (1254 × 1254; four suit columns × three rank rows).
- ../../assets/classic/specials.png (1448 × 1086; four columns × three rows).

Original assets remain in assets/matte. No image API scripts or dependencies added to the game. Exact production prompts: production-prompts.txt. Initial review prompt: prompt.txt.

## Validation

JavaScript syntax and git diff whitespace checks passed. Chromium checked widths 320, 390 and 1280 px; all 40 cards, exact central pip counts, point values, Pocha point hiding, 12 court variants, matching card dimensions and frame insets, actual card play, Capitán selection, suit/seat targets, spending a special card and opening a chest. Light/dark screenshots inspected; corrected central pip crowding found in the first visual pass.

Browser checks ran offline with external requests blocked. The existing Firebase initialization consequently reported `firebase is not defined`; no gameplay JavaScript errors followed. Multiplayer/network behavior was not exercised.
