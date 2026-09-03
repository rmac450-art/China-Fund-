# China Fund

A weekly spending tracker for a savings goal. It ships with an example budget —
**$5,920 by 16 December 2026**, eight category caps totalling **$115.04/wk** against
**$509.72/wk** of net income — but every one of those numbers is editable under
**Settings**, so anyone can point it at their own goal.

Commute spending is tracked separately from discretionary transport, because it protects
the income that funds the goal.

## Settings

Everything the maths runs on is editable, per device:

| Field | Meaning |
|---|---|
| Net income / week | What lands in the account each week |
| Start date | First day of week 1 |
| Saving stops | The final day — week count follows from it |
| Already saved | An opening balance; counts toward the goal from day one |
| Savings goal | Leave blank to derive it from income, caps and dates |
| Category caps | Add, rename, remove; the weekly cap is the sum |

A preview strip inside the panel recalculates as you type — week count, goal, what you'd
have banked today and the projected total — so you can see what a date change does before
committing it. It also warns when a change would push already-logged entries outside the
window, where they stop counting.

Note that an explicitly typed goal is **pinned**: it stays put when you change the dates.
Clear the field to go back to a goal that follows your income, caps and dates.

## "Left this week"

This is your **spending allowance** minus what you've logged — the $115.04/wk of category
caps, not the full $509.72 of net income. The other $394.68 is what the fund is made of,
so it is deliberately not offered as spendable. The figure turns red and goes negative
once you pass the allowance.

The stats strip follows whichever week you have open, and its labels say so ("Left week 4"
rather than "Left this week") when you've navigated away from the current one.

## How the projection works

**Projected total** is what you'd finish with. Future spending is assumed at your weekly
cap to begin with, and shifts onto your actual observed rate over the first four weeks —
extrapolating a couple of sparse weeks across the whole term flatters the number badly,
so the observed rate has to earn its place. The caption under the figure always says which
assumption is currently in play.

It counts your **Already saved** balance, so it is the total you'd *hold*, not the amount
you'd *add*. If your goal figure means "money added from here", the projection will sit
above it by roughly your opening balance — that's the two numbers measuring different
things, not an error.

## How income is counted

A week's income lands in the totals when that week **finishes**, not day by day. So
"Banked so far" only ever counts money you've actually been paid, and can be compared
directly with your bank balance. The figure steps up once a week rather than creeping
daily; the status line tells you when the next payment lands.

Spending, by contrast, counts the moment you log it. A week still in progress therefore
shows a negative "Saved" figure marked with `*` until its income arrives.

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
