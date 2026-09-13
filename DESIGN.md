# Ember design direction

Direction transcribed from the owner's brief. Specific values (palette, type, motion timings) were chosen by the agent and are marked so; change them freely.

## Brief (owner's words, paraphrased)

Ultra-minimal todo list. Bare minimum UI. Browser only, local storage only. Something that builds a streak and makes the app worth coming back to. Very clean, seamless animation.

## Design read

Reading this as: a single-screen personal utility for one person, in a warm ultra-minimal style, dial ENERGY 1 / RHYTHM 1 / MOTION 2.

- ENERGY 1: the list is the product. Nothing competes with the input box and the tasks.
- RHYTHM 1: one screen, one column, no sections. Uniformity is the point.
- MOTION 2: motion only on state change (add, finish, remove, reorder, streak lights). No loops, no ambient movement. Reduced-motion preference disables all of it.

## Identity motif (agent chosen)

The ember. One dot at the top: filled and glowing while the streak is alive, a hollow ring when it is cold. Lit and cold differ in shape as well as colour. The same orange is used in exactly three places: the ember, a finished task's mark, and keyboard focus. Nowhere else.

## Palette (agent chosen)

Warm paper, not white. Warm ink, not black. One accent.

| Role | Light | Dark |
|------|-------|------|
| Paper | #faf7f2 | #141210 |
| Ink | #1d1a17 | #efe9e2 |
| Muted text | #6e665e | #a39b92 |
| Rule line | #e6e0d8 | #2a2622 |
| Ember (accent) | #c9501c | #ff7a3d |
| Cold ember | hollow ring in Muted text colour | hollow ring in Muted text colour |

Why warm: an ember belongs on paper, not on a screen-blue white. Why one accent: the streak is the only thing that needs to be noticed.

Theme follows the operating system setting. No in-app toggle, because the brief is "bare minimum UI" and the OS already offers the choice.

## Typography (agent chosen)

System UI stack. Reasons: zero network requests keeps the app instant and offline, and a personal list should look native to whatever device it lives on. Task text is slightly larger than UI text so the list reads before the chrome.

## Spacing

One column, max 30rem wide, generous top margin. Rows are separated by hairlines, not cards. Whitespace does the grouping.

## Motion (agent chosen)

- New task: fades and slides in from the input, 220ms.
- Finish: the mark fills and the text strikes, then the row glides to the bottom (FLIP), 260ms.
- Remove: the row collapses, 200ms.
- Ember: scales up once when the streak advances. Static glow while lit. Never pulses.
- `prefers-reduced-motion: reduce` turns all of the above off.
