# Ember

A todo list that is only as complicated as a list needs to be.

One box to type in. One tap to finish. Everything stays in your browser's local storage. No account, no server, no sync.

The one extra: a streak. Finish at least one task a day and the ember at the top keeps burning. Miss a day and it goes cold.

## Run it

Open `index.html` in a browser. That is the whole install.

If your browser blocks local storage on `file://` pages, serve the folder instead:

```bash
python3 -m http.server 8765
```

then open http://localhost:8765.

## How the streak works

- Finish at least one task and today counts. The ember lights.
- Finish one tomorrow and the streak grows. Skip a day and it goes out.
- Your best run is remembered and shown when the ember is out.
- Days are counted in your device's local time.

## Keyboard

- Type and press Enter to add. Escape clears the box.
- Tab to a task, Enter or Space to finish it. The next stop is its remove button.

## Design

See [DESIGN.md](DESIGN.md) for the direction, palette, and motion rules. The UI was built under the [anti-slop](https://github.com/miqdadbadjuber/anti-slop) rules.

## License

MIT.
