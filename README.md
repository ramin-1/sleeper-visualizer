# sleeper-visualizer

Live league-median standings for a Sleeper fantasy football league.

Enter a league ID and see the current week sorted against the league median —
the top half banks an extra win, the bottom half an extra loss.

- **Live points** — where the cut line sits right now.
- **Projected final** — Sleeper's own live projection formula, ported from their
  web app: each starter's pre-game projection blended toward their current scoring
  pace as the game clock runs down. Matches the number Sleeper displays to the cent.

Projections are scored with your league's own `scoring_settings`, not a
generic PPR total.

Open `index.html` directly, or visit the Pages deployment.
`index.html?test` runs the median/projection self-checks.
