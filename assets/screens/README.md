# App screenshots used on the site

The site loads `assets/screens/<look>-<screen>.jpg`. Keep these exact file names when
replacing images; the page's look switcher builds the path from them.

Current files are **stand-ins** from the stage build (admin account, mostly empty data).
Replace them with shots from the populated demo account.

## Capture spec

- Portrait phone screenshot, **495 x 1100 px** (9:20). Larger at the same ratio is fine;
  export as JPG, quality ~75-80, ideally under 80 KB each.
- Include the status bar; the site draws the phone frame and a dynamic-island cutout over the
  top-centre, so keep nothing important in the top ~40 px centre.
- Demo account: a real-looking household name (not "Admin"), a filled week plan, a pantry
  with items, and a real (non-placeholder) shopping list.

## Slots (7 screens x 2 looks = 14 files)

| Screen slot | Where it shows on the site | What to capture | classic file | inverted file | Stand-in source |
|---|---|---|---|---|---|
| `home` | Hero phone | Home tab, top: greeting, today's date, today's meals filled in | `classic-home.jpg` | `inverted-home.jpg` | `*-01-home` |
| `meals` | Tour step 1 (Plan) | Meals hub, or better a filled week plan / calendar | `classic-meals.jpg` | `inverted-meals.jpg` | `*-03-meals-hub` |
| `pantry` | Tour step 2 (Pantry) | Pantry with several items plus quick-add chips visible | `classic-pantry.jpg` | `inverted-pantry.jpg` | `*-07-pantry` |
| `shopping` | Tour step 3 (Shop) | Shopping list from the plan, grouped by aisle, with store price estimates loaded | `classic-shopping.jpg` | `inverted-shopping.jpg` | `*-09-shopping-scrolled` (placeholder list) |
| `cook` | Tour step 4 (Cook) | Cook mode mid-recipe (a real step and timer), ideally with Safe Cooking Temperatures open | `classic-cook.jpg` | `inverted-cook.jpg` | `*-10-cooking` (no recipe selected) |
| `household` | Tour step 5 (Household) | Household votes with some votes cast, or Dish Suggestions with suggestions | `classic-household.jpg` | `inverted-household.jpg` | `*-02-home-scrolled` |
| `settings` | Tour step 6 (Looks) | Settings > Appearance with the four look chips visible | `classic-settings.jpg` | `inverted-settings.jpg` | `classic-11-settings` for **both** (the stage inverted build rendered Settings in a light skin) |

Notes:

- `inverted-settings.jpg` is currently a copy of the classic shot. Capture a real inverted one.
- The settings stand-in shows the admin email; the final shot should use the demo account.
- `classic-home.jpg` is also embedded in `og-image.svg`; re-render `og-image.png` after replacing it
  (see the repo README).
- Adding the `redesign` or `editorial` looks later: add `redesign-<screen>.jpg` for all seven slots,
  add the look name to `LOOKS` in `index.html`, and add a matching button and CSS token block.

## Capture status (2026-10-02)

Final shots from the stage build at main 83a04f3 (account display name "Sam", no email in frame):

- Final: `pantry` and `settings` (both looks; the inverted Settings shot is a real capture with
  "inverted" selected; Settings itself still renders light in that look), `meals` (hub, no plan),
  and `cook` (Safe Cooking Temperatures open; no recipe until the new catalog is on stage).
- Still stand-ins: `home`, `shopping`, `household`. These need a real week plan, which needs the
  rewritten recipe catalog on stage, plus the stage API deploy that removes the old starter grocery
  list. Re-capture `meals` and `cook` mid-recipe at the same time.
