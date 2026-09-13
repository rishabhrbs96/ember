# Ember

A todo list that is only as complicated as a list needs to be.

One box to type in. One tap to finish. Everything stays in your browser's local storage. No account, no server, no sync.

The one extra: a streak. Finish at least one task a day and the flame at the top keeps burning. Miss a day and it goes out.

## Views

- **Today** is the default. Unfinished one-off tasks from the day before carry over. Kindling items are added fresh each morning.
- **Kindling** is the recurring list. Anything here starts every new day's list. It is what you use to get the fire going.
- **History** shows the last 30 days as a strip of embers, lit on days you finished something, and one collapsible row per past day with what got done and what did not.
- **Data** shows what is stored and how much space it takes, and lets you export it as JSON, stop saving, or erase everything.

## Run it

Open `index.html` in a browser. That is the whole install.

If your browser blocks local storage on `file://` pages, serve the folder instead:

```bash
python3 -m http.server 8765
```

then open http://localhost:8765.

## Your data

Ember asks once, on first run, before it writes anything to your browser. Say no and the list lives in memory until you close the tab. You can change your mind under Data.

What is stored: your tasks by day, Kindling, the streak, and your theme choice. Days older than two years are dropped. Nothing is transmitted anywhere. There are no cookies and no analytics.

## How the streak works

- Finish at least one task and today counts. The flame lights and the numeral goes up.
- Finish one tomorrow and the streak grows. Skip a day and it goes out.
- Your best run is remembered and shown when the flame is out.
- Days are counted in your device's local time.

## Keyboard

- Type and press Enter to add. Escape clears the box.
- Tab to a task, Enter or Space to finish it. The next stop is its remove button.
- Dim and Bright switch the theme. Without a choice, Ember follows your OS.

## Design

See [DESIGN.md](DESIGN.md) for the direction, palette, and motion rules. The UI was built under the [anti-slop](https://github.com/miqdadbadjuber/anti-slop) rules.

## License

MIT.
