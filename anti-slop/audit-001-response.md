# Response to audit 001, 13 September 2026

Every finding was read. Applied unless it collided with a decision the owner had already made, in which case the collision is named and the finding left open.

| # | Finding | Action |
|---|---------|--------|
| 1 | Clear done rewrites the day | Applied. Control, handler, and styles removed. |
| 2 | Midnight breaks adding | Applied. Today's list is created on demand and a timer rolls the day at midnight. |
| 3 | Keyboard focus lost after finish or remove | Applied. Focus returns to the task, or moves to a neighbour after remove. |
| 4 | Later-day controls fail contrast | Applied. Opacity rules removed; muted at full strength. |
| 5 | Paper on light ember fails | Applied. Light ember is #bf4a1a (4.67:1). Favicon and DESIGN updated. |
| 6 | Streak stated four times | Applied. Date line carries the task count, the hearth carries the streak, the empty-list note is gone. |
| 7 | Three ways to tomorrow, keyboard trap | Partly. Owner asked for an any-day option, so the calendar stays; it is now one button that opens the picker and the date input is out of the tab order. Placeholder shortens again under 300px. |
| 8 | Consent dialog blocks first use | Declined. Owner asked for consent on first run. |
| 9 | Two theme controls, tagline in heading | Partly. Owner asked for both a header theme switch and the tagline. The tagline moved out of the h1 into its own element. |
| 10 | History lists the same days twice | Partly. The bar is gone; rows keep the tally. Rows still cover recent days because the dots carry no text. |
| 11 | Settings shows diagnostics | Partly. Lead cut to one sentence, footnote removed. The three facts stay: the owner asked that people be told what is stored. |
| 12 | Wrapped task strikes one line | Applied. Text-decoration strike; mark on the first line. |
| 13 | Add for tomorrow gives no confirmation | Applied. The waiting line sits directly under the input. |
| 14 | Nav shifts when numeral appears | Applied. |
| 15 | Font flash | Applied. Both files preloaded. |
| 16 | Page cached twice | Applied. |
| 17 | Manifest theme colour | Applied. Paper. |
| 18 | Fuel rows decorated, lead repeats | Applied. |
| 19 | Accent strays | Applied for the selected choice and the hover. The part-done ring stays as a state encoding and is now listed in DESIGN. |
| 20 | Docs drift | Applied. |
| 21 | Glow re-rasterised each frame | Applied. Static blurred disc behind the SVG. |
| 22 | enterkeyhint says Done | Applied. Removed. |
| 23 | Buttons announce state twice | Applied. |

Not re-measured after the fixes: install on iOS, import through a real file dialog, reduced-motion. Those match the audit's own list.
