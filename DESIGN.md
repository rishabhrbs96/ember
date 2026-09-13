# Ember design direction

Direction transcribed from the owner's brief. Specific values (palette, type, motion timings) were chosen by the agent and are marked so; change them freely.

## Brief (owner's words, paraphrased)

Ultra-minimal todo list. Bare minimum UI. Browser only, local storage only. Something that builds a streak and makes the app worth coming back to. Very clean, seamless animation.

## Design read

Reading this as: a single-screen personal utility for one person, in a warm ultra-minimal style, dial ENERGY 1 / RHYTHM 1 / MOTION 2.

- ENERGY 1: the list is the product. Nothing competes with the input box and the tasks.
- RHYTHM 1: one screen, one column, no sections. Uniformity is the point.
- MOTION 2: motion on state change (add, finish, remove, reorder, streak lights). Reduced-motion preference disables all of it.
- One owner-requested exception: the lit flame flickers gently on a loop. The owner asked for fire animation as the app's identity, so this is recorded as a deliberate override of the no-endless-loops rule. It is the only looping motion on the page and it marks a real state (the streak is alive).

## Identity motif (owner direction, agent execution)

Fire. A flame at the top: filled, glowing, and flickering while the streak is alive, an outline when it is out. Beside it the streak numeral. A small outline flame marks tasks that came from Kindling. History shows each day as a small ember, lit or not. Lit and cold always differ in shape as well as colour.

The orange is used for: the lit flame, a finished task's mark, lit day embers, the active view's underline, and keyboard focus. Nowhere else.

## Vocabulary

- Kindling: the recurring list that starts every day. Chosen over "master list" because it says what the list is for, not what it is.
- Lit / out: the streak states. "Burning" for the count line.
- Dim / Bright: the theme switch labels. They name the action, not the mode.

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

Theme follows the operating system until the person picks Dim or Bright. The choice is remembered.

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

## Views

One screen, four tabs as plain text: Today, Kindling, History, Data. Today is default because the app's whole job is today. Tabs are text, not icons, because four words are clearer than four glyphs at this size.

## Data and consent

A first-run dialog explains that everything stays in the browser and asks before anything is written. It is the only raised surface in the app, hence the only shadow. The primary button is ink on paper rather than orange, so the accent keeps its meaning. The Data view shows exactly what is stored and offers export, stop, and erase.
