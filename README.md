# Ember

*Keep the fire within.*

A todo list that is only as complicated as a list needs to be.

One box to type in. One tap to finish. Everything stays in your browser's local storage. No account, no server, no sync.

The one extra: a streak. Finish everything on the day's list and the flame at the top burns. Leave something undone and it goes out.

## Views

- **Today** is the default. Unfinished one-off tasks from the day before carry over. Fuel items are added fresh each morning. Type a task and press "Add for tomorrow", or the calendar for any later day; a line under the list shows what is waiting.
- **Fuel** is the recurring list. Anything here is on every new day's list. It is what you feed the fire.
- **History** is a calendar, one month at a time. Each day's fill shows how it went; tap a day to see exactly what got done.
- **Settings** holds the theme choice and your data: what is stored, how much space it takes, export or import as JSON (merge or replace), stop saving, or erase everything.

The line beside the flame changes with your streak, from "Light it up." to "Nothing puts you out."

## Install it as an app

Ember is a web app that installs like a native one, with no store in between. Open the site, go to Settings, and follow the Install row: it shows an Install button where the browser offers one (Chrome, Edge, Android), and the Share then Add to Home Screen steps on iPhone and iPad. Once installed it opens full screen from the home screen and works offline.

For that to work the site has to be served over https. GitHub Pages does this for free: in the repository settings, under Pages, choose the main branch and the root folder.

## Run it

Open `index.html` in a browser. That is the whole install.

If your browser blocks local storage on `file://` pages, serve the folder instead:

```bash
python3 -m http.server 8765
```

then open http://localhost:8765.

## Your data

Ember asks once, on first run, before it writes anything to your browser. Say no and the list lives in memory until you close the tab. You can change your mind under Settings.

What is stored: your tasks by day, Fuel, the streak, and your theme choice. Days older than two years are dropped. Nothing is transmitted anywhere. There are no cookies and no analytics. The two typefaces ship with the app, so not even a font request leaves your device.

## How the streak works

- A day counts when every task on its list is done. The flame burns and the numeral goes up.
- Until today's list is done the flame is warm: your streak is alive but not yet extended. Leave the list unfinished at midnight and it goes out.
- Adding a task after the list was done makes the flame warm again until that task is done too.
- Your best run is remembered and shown when the flame is out.
- Days are counted in your device's local time.

## Keyboard

- Type and press Enter to add. Escape clears the box.
- Tab to a task, Enter or Space to finish it. Focus stays on the task; the next stop is its remove button.
- Escape closes any dialog.
- In History, Tab reaches the calendar once; arrow keys move between days, PageUp and PageDown between months.
- Dim and Bright switch the theme from the header or Settings. Without a choice, Ember follows your OS.

## Sizes

One column from a watch face to a wide monitor. On phones the views sit in a bar at the bottom of the screen. Type scales down below 400px and again below 290px, and up above 900px and 1600px. All motion is transform and opacity only, and switches off under the reduced-motion setting.

## Design

See [DESIGN.md](DESIGN.md) for the direction, palette, and motion rules. The UI was built under the [anti-slop](https://github.com/miqdadbadjuber/anti-slop) rules.

## License

MIT for the app. The typefaces Ranade and Satoshi are by the Indian Type Foundry under the Fontshare Free Font License, see `fonts/LICENSE.txt`.
