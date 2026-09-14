# Response to audit 002, 13 September 2026

| # | Finding | Action |
|---|---------|--------|
| 1 | Bottom bar covers the last row on phones | Applied. Narrow rules set only top and side padding now. |
| 2 | Screen reader hears the streak without its number | Applied. The whole streak line is the status region; the numeral is in it. |
| 3 | Views open at the previous scroll offset | Applied. Every view and day page opens at the top. |
| 4 | Day one loses its streak when a task is added | Applied. The day the flame lit is recorded; the streak holds at one or more while today is reopened. Documented in DESIGN. |
| 5 | Offline copy never refreshed | Applied. Response cloned before the cache opens, both branches. Cache name bumped. |
| 6 | theme-color ignores Dim/Bright | Applied. One meta, set from the computed paper colour on every theme change. |
| 7 | Filled ink segment is the heaviest mark | Applied. Active segment is a rule-colour tint with an ember icon and ink text, the phone bar's treatment. |
| 8 | Grid is 35 tab stops | Partly. The grid is one Tab stop with arrow, Home, and End keys. The rows stay: they carry the tally in text and are the touch path to a day. |
| 9 | Fuel explained three times | Applied. Placeholder only. History's lead appears once seven days are listed. |
| 10 | Done said three times; two rungs alike | Applied. "Today is done" left the streak line; the first rung is "First light." |
| 11 | Waiting line is a row of its own | Applied. It is now part of the date line ("3 left. 1 for tomorrow.") and opens the same list. |
| 12 | Every finished row shows its cross | Applied. Hover and focus reveal it; touch devices still show it. |
| 13 | Desktop nav carries icons and labels | Kept. With finding 7 the icon carries the state. |
| 14 | Page shifts when the scrollbar appears | Applied. |
| 15 | Toggle re-measures the whole list | Applied. The glide is skipped past forty rows. |
| 16 | Consent dialog names Fuel; note shows behind it | Applied. |
| 17 | Settings facts read oddly | Applied. |
| 18 | Day page says its total twice | Applied. |
| 19 | A far-day task lives forever | Applied. The picker allows one year ahead. |
| 20 | Input underline twice the weight | Applied. 1px at rest, 1.5px ember when focused. |
| 21 | Docs | Applied. |

Decisions questioned again (calendar button, first-run consent, header theme link): unchanged. They are the owner's, and the owner has confirmed each once already.
