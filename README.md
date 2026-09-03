# China Fund

A weekly spending tracker for a savings goal. It ships with an example budget —
**$5,920 by 16 December 2026**, eight category caps totalling **$115.04/wk** against
**$509.72/wk** of net income — but every one of those numbers is editable under
**Settings**, so anyone can point it at their own goal.

Commute spending is tracked separately from discretionary transport, because it protects
the income that funds the goal.

## Logging something you forgot

The date field is bounded to the fund's window, so the picker won't offer an impossible
day. Backdating within the window just works — the app jumps to whichever week the date
falls in and tells you it did. If the date is *before* the fund started, it offers to pull
the start date back in whole weeks, which keeps the existing week boundaries and end date
exactly where they were (the goal rises, since you've added a week of saving).

The entries card has a **This week / All** toggle. **All** lists every entry you've ever
logged, grouped by week — use it when you're not sure whether something got recorded.

## Use it

Open the published page, then on iPhone: **Share → Add to Home Screen** for a fullscreen
app icon. On Android: **Install app** from the Chrome menu.

## Privacy

There is no server and no account. Entries and your budget settings live in `localStorage`,
which the browser scopes to this site on that one device. Two people using the same link
on their own phones cannot see each other's data — it never leaves the phone it was typed
on. Use **Export CSV** to back up, or to move to a new device.

The trade-off: clearing browser data wipes your entries, and nothing syncs between your
own devices. Export a CSV every so often.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole app — markup, styles, logic |
| `sw.js` | Service worker; caches the shell so it opens offline |
| `manifest.webmanifest` | Home-screen name, icon, standalone display |
