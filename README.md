# The Tape

A stock research dashboard — real price history, returns, a transparent rules-based trend
signal, and plain-English investing guidance for 54 well-known stocks from the US, Europe,
Asia and beyond. Not financial advice.

This is a single self-contained `index.html` file: no build step, no server, no dependencies
beyond two Google Fonts links loaded over the network.

## Publish it on GitHub Pages

1. Create a new GitHub repository (or use an existing one).
2. Add `index.html` to the root of the repo (that exact name and location matter for the
   simplest setup).
3. Commit and push.
4. On GitHub, go to **Settings → Pages**.
5. Under **Build and deployment → Source**, choose **Deploy from a branch**.
6. Under **Branch**, choose your default branch (e.g. `main`) and folder `/ (root)`, then
   **Save**.
7. GitHub shows a URL like `https://<your-username>.github.io/<repo-name>/` — it usually
   goes live within a minute or two.

## About the data

The prices, returns, moving averages and trend signal are a real snapshot pulled from Yahoo
Finance, not a live feed — static HTML/JS can't call financial APIs directly. The page says so
in its own header. If you want the data refreshed, the simplest path is to ask Claude to pull
fresh data and regenerate the file again; there's no "auto-refresh" built in.

## The built-in chat assistant

There's an "Ask about stocks" button in the top-left. It depends on a Claude-specific
capability (`window.claude.use("sample")`) that only exists inside the claude.ai Artifact
viewer. Hosted on GitHub Pages (or anywhere outside claude.ai), it will render but show a
graceful "not available in this view" message instead of answering — this is expected, not a
bug, and nothing else on the page is affected.
