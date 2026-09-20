# sleeper-visualizer

Live league-median standings for a Sleeper fantasy football league.

Enter a league ID and see the current week sorted against the league median —
the top half banks an extra win, the bottom half an extra loss.

- **Live points** — where the cut line sits right now.
- **Projected final** — points banked so far plus each starter's projection
  scaled by the time left in their real NFL game.

Projections are scored with your league's own `scoring_settings`, not a
generic PPR total.

Open `index.html` directly, or visit the Pages deployment.
`index.html?test` runs the median/projection self-checks.
