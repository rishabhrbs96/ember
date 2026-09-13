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

Fire. The name sits small at the top like a native app title. Below it the hearth: a large flame, the one focal point on every screen, with two layers, an outer tongue and a paler inner one, each flickering at its own pace while the streak is alive, an outline when it is out. Its glow grows with how much of today is finished. Beside it, one line addressed to the person that changes with the streak ("Light it up." through "Nothing puts you out."), then the streak numeral. The same flame is the favicon. A small outline flame marks tasks that came from Fuel. History shows each day as a small ember, lit or not. Finishing a task throws five sparks off the mark. Lit and cold always differ in shape as well as colour.

The orange is used for: the lit flame, a finished task's mark, lit day embers, the active view's underline, and keyboard focus. Nowhere else.

## Vocabulary

- Fuel: the recurring list that goes on every day. Chosen over "master list" and "kindling" because everyone knows what fuel does to a fire.
- Out / warm / burning: the flame states. Out means no streak. Warm means the streak is alive but today's list is not finished. Burning means today is done.
- Done: a day counts when every task on it is finished. Finishing one thing is not enough to keep a fire going.
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

One screen, four views: Today, Fuel, History, Settings. Today is default because the app's whole job is today.

On wide screens the views are a segmented control under the hearth, the active segment filled with ink so there is no ambiguity in either theme. On phones (under 700px) the same control becomes a fixed bar at the bottom of the screen, where thumbs are, each view an icon over a label, the active icon in ember. On watches the labels hide and the icons stay. The four icons are drawn for this app: a checked circle, the flame, three dots for the strip of days, two sliders.

## Sizes

Type scales with the device through the root font size: 87.5% under 290px (watches), 93.75% under 400px (phones), 106.25% above 900px, 118.75% above 1600px. The column widens from 30rem to 34rem on wide screens. Nav wraps on watches. Nothing else changes shape, because the layout is one column everywhere.

## Motion budget

Motion only where it shows cause and effect. Every animation is transform, opacity, or background-size, so it stays cheap.

- Add: the row slides in from the input.
- Finish: the mark fills, three sparks leave it (500ms), the row glides to the bottom. When the last task tips today into done, the flame flares and starts to burn. Adding or unfinishing a task after that settles it back to warm.
- Remove: the row slides out.
- Focus the input: the ember underline draws in from the left.
- Open History: 35 embers fill in over 210ms, left to right, like days passing.
- The flame flickers while lit and its glow tracks today's completion.

No fades on view switches, no ambient movement anywhere else. All of it is off under prefers-reduced-motion.

## Data and consent

A first-run dialog explains that everything stays in the browser and asks before anything is written. It is the only raised surface in the app, hence the only shadow. The primary button is ink on paper rather than orange, so the accent keeps its meaning. The Data view shows exactly what is stored and offers export, stop, and erase.

## History

Three layers, because a person asks three different questions of their past. The five-week grid answers "how consistent am I", each day an ember: faint when nothing was listed, hollow when nothing got done, ember ring when some did, filled when all of it did. The rows answer "how did a given day go", with a bar and a tally. A page per day answers "what exactly happened", grouped into done and not done, so a long list never has to fold into an accordion. Older days load thirty at a time.

## Today

A date line at the top, in words, with the streak day next to it ("Saturday, 13 September. Day 4 of your streak."), so the page reads like the top of a journal entry.
