# Kaun Banega Crorepati — Stable Money leaderboard

Live quiz leaderboard. Single self-contained `index.html`: no build step, no
dependencies, no backend. Deployed as a static site.

## How it gets its data

The page reads the quiz response sheet as CSV in the browser and re-ranks on a
30 second poll. Ranking is most correct answers first, ties broken by the
faster clock, then by whoever submitted earliest.

Everything configurable sits in the `CONFIG` block at the top of the `<script>`
in `index.html` — sheet id, the published CSV URL, and the refresh interval.

Columns are matched by header **name**, not position, so reordering columns in
the sheet will not break the board.

## Local preview

    python3 -m http.server 8000
    # then open http://localhost:8000

Append `?demo=1` to the URL to render sample contestants instead of live
entries — useful for checking the layout without touching the sheet.
