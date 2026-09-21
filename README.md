# sleeper-visualizer

Live league-median standings for a Sleeper fantasy football league.

**[ramin-1.github.io/sleeper-visualizer](https://ramin-1.github.io/sleeper-visualizer/)**

Enter a league ID and see the current week sorted against the league median —
the top half banks an extra win, the bottom half an extra loss.

- **Live points** — where the cut line sits right now.
- **Projected final** — Sleeper's own live projection formula, ported from their
  web app: each starter's pre-game projection blended toward their current scoring
  pace as the game clock runs down. Matches the number Sleeper displays to the cent.

Click any team to expand their starting lineup: each slot, the player's game
status, their stat line, points banked, and their live projection — green if they
are now projected above their pre-game number, red if below. Expanded rows
survive the auto-refresh.

The team projected to finish first is crowned as the week's leader, since first
place each week pays a $10 bonus.

Projections are scored with your league's own `scoring_settings`, not a
generic PPR total.

Your league ID is the number in the Sleeper URL:
`sleeper.com/leagues/<league id>/team`. It is remembered between visits, and the
week and mode live in the query string, so a bookmark like
`?league=<league id>&mode=proj` opens straight to the standings — leave `week` off
and it follows the current NFL week.

Scores and the game clock refresh every 30 seconds while the tab is visible;
projections refresh every 10 minutes, matching how often Sleeper republishes them.

Runs as a single static file with no build step and no dependencies, so opening
`index.html` locally works too. `index.html?test` runs the self-checks, including
four live projections checked against the values Sleeper's own app displayed.
