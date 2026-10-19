# sleeper-visualizer

Live league-median standings for a Sleeper fantasy football league.

**[ramin-1.github.io/sleeper-visualizer](https://ramin-1.github.io/sleeper-visualizer/)**

Enter a league ID and see the current week sorted against the league median —
the top half banks an extra win, the bottom half an extra loss.

The **Live | Proj** toggle at the top chooses what everything is scored on (the Live
and Proj column headers do the same):

- **Live points** — where the cut line sits right now.
- **Projected final** — Sleeper's own live projection formula, ported from their
  web app: each starter's pre-game projection blended toward their current scoring
  pace as the game clock runs down. Matches the number Sleeper displays to the cent.

Click any team to expand their matchup, laid out like Sleeper's: both teams' scores and
projections up top with each side's win probability (Sleeper's own formula, as a
bar sized to the odds), then their roster beside their opponent's — starters aligned by
slot, each with game status,
stat line, points banked, and live projection — green if they are now projected
above their pre-game number, red if below — followed by bench, injured reserve
and taxi, dimmed since they do not score. Expanded rows survive the auto-refresh.

If the page is redeployed while you have it open, a notice appears offering a
reload. A tab left open all Sunday would otherwise keep running old code.

The team projected to finish first is crowned as the week's leader, since first
place each week pays a $10 bonus.

The **Standings** tab shows the season standings after this week: each team's record
with this week's head-to-head and median results added, PF and PA with this week's
scores added, the move from the current standings (▲▼), and the playoff line. Every
column sorts, and clicking again reverses it. A past week is already in Sleeper's
season totals, so for those it shows the actual standings rather than adding it twice.

**Chopped (guillotine) leagues** are detected automatically. Instead of the
median race the page shows the chopping block: only surviving teams are ranked,
the lowest is marked as on the block, the Cushion column shows how far each team
sits above last place (and what the last-place team needs to escape), and teams
already cut are listed underneath with the week they went. A FAAB column shows each
team's remaining waiver budget; click it to order the rows by money left (ranks,
cushions and the chopping block still come from the scores). There's no
head-to-head, so expanding a team shows just its roster.

Projections are scored with your league's own `scoring_settings`, not a
generic PPR total.

Add your Sleeper username and every league you're in this season appears in the
league menu, looked up fresh each visit so new leagues just show up. To follow a
league you're not in — a friend's, say — add its league ID instead (the number in
`sleeper.com/leagues/<league id>/...`); it's saved under "Saved leagues" with a ✕
to remove it. Both are kept in your browser's storage, so they're per browser and
per device and don't sync between your phone and laptop.

The league, week and mode also live in the query string, so a bookmark like
`?league=<league id>&mode=proj` opens straight to the standings — leave `week` off
and it follows the current NFL week.

Scores and the game clock refresh every 30 seconds while the tab is visible;
projections refresh every 10 minutes, matching how often Sleeper republishes them.

Runs as a single static file with no build step and no dependencies, so opening
`index.html` locally works too. `index.html?test` runs the self-checks, including
four live projections checked against the values Sleeper's own app displayed.
